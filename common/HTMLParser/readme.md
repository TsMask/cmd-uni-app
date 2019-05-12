### HTML 文本解析器

用于解析请求网络地址得到的text文本，通过HTML的DOM方式获取节点字符数据。
 
**DOM操作属性说明：**
* 首先将请求获取得到的HTML文本text字符串，通过``new HTMLParser(text)``实例化为DOM操作对象。
* 后通DOM操作属性获取节点的HTML文本字符信息。

|属性名																																										|返回类型	|默认值	|说明															|
|---																																											|----			|---		|---															|
|[getElementsByTagName](http://www.w3school.com.cn/jsref/met_doc_getelementsbytagname.asp)|Array		|-			|带有指定标签名的对象							|
|[getElementsByClassName](http://www.w3school.com.cn/jsref/met_doc_getelementsbyname.asp)	|Array		|-			|带有指定样式名称的对象						|
|[getElementById](http://www.w3school.com.cn/jsref/met_doc_getelementbyid.asp)						|Array		|-			|对拥有指定 id 的第一个对象的引用	|

**使用方式：**

在 ``script`` 中引用html-parser.js文件即可

```javascript
import HTMLParser from "@/common/HTMLParser/html-parser.js"
```

**用法：**
有些地址需要跨域才能访问
```javascript
mounted() {
  // 调用
  this.parserData().then(res =>{
    console.log("res: ", res);
  });
},
methods: {
  // 异步等待解析数据
  async parserData() {
      const jsonData = {};
      // 请求数据
      const [error, res] = await uni.request({
          url: 'https://ext.dcloud.net.cn/'
      });
      // 成功返回
      if (res) {
          // 数据存放
          const pluginTitle = [];
          // 获取HTML文本转DOM操作
          const doc = new HTMLParser(res.data.toString().trim());
          // 选取插件列表内层的HTML文本
          const pluginListText = doc.getElementsByClassName('plugin-list')[0].innerHTML;
          // 获取插件列表数据转DOM操作
          const pluginArrayDoc = new HTMLParser(pluginListText).getElementsByTagName('li');
          // 遍历每个插件对象
          for(let plugin of pluginArrayDoc){
              // 插件对象HTML文本转DOM操作
              let pluginDoc = new HTMLParser(plugin.innerHTML);
              // 获取插件标题转DOM操作
              let pluginTitleDoc = new HTMLParser(pluginDoc.getElementsByClassName('extend-title')[0].innerHTML);
              pluginTitle.push(pluginTitleDoc.getElementsByTagName('a')[0].innerHTML);
          }
          // 返回数据
          jsonData.errMsg = "请求成功"
          jsonData.data = pluginTitle;
      }
      // 失败返回
      if (error) {
          jsonData.errMsg = "暂无数据"
          jsonData.data = "null";
      }
      // 返回数据对象
      return jsonData
  }
}
```

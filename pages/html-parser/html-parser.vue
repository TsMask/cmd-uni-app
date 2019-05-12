<template>
  <view>
    <view style="background: #f5f5f5;">
      HTML 文本解析器-等一下网络响应
    </view>
    <view class="" v-for="t in title" :key="t">
      {{t}}
    </view>
  </view>
</template>

<script>
  import HTMLParser from "@/common/HTMLParser/html-parser.js"
  export default {
    data() {
      return {
        title: []
      };
    },
    onLoad() {
      // 触发请求数据
      this.parserData().then(res => {
        console.log(JSON.stringify(res));
        this.title = res.data;
      });

    },
    methods: {
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
          for (let plugin of pluginArrayDoc) {
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
  }
</script>

<style>

</style>

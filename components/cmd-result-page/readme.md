### ResultPage 结果页

结果页组件，组件名：``cmd-result-page``，代码块： cmdResultPage。

**使用方式：**

在 ``script`` 中引用组件 

```javascript
import cmdResultPage from "@/components/cmd-result-page/cmd-result-page.vue"
export default {
    components: {cmdResultPage}
}
```

用法

```html
<!-- 默认 -->
<cmd-result-page></cmd-result-page>
<!-- 页面丢失 -->
<cmd-result-page type="lost"></cmd-result-page>
<!-- 网络异常 -->
<cmd-result-page type="network"></cmd-result-page>
<!-- 按钮列表 -->
<cmd-result-page def-btn="再试一次" @defBtn="fnClick"></cmd-result-page>
<cmd-result-page warn-btn="重启" @warnBtn="fnClick" ></cmd-result-page>
<cmd-result-page pri-btn="确认成功" @priBtn="fnClick"></cmd-result-page>
<cmd-result-page def-btn="返回" @defBtn="fnClick" pri-btn="再来一次" @priBtn="fnClick" warn-btn="终止" @warnBtn="fnClick"></cmd-result-page>
<!-- 自定义图案 -->
<cmd-result-page src="https://gw.alipayobjects.com/zos/rmsportal/HWuSTipkjJRfTWekgTUG.svg" text="等待处理" subtext="已提交申请，等待银行处理"></cmd-result-page>
```
 
**属性说明：**

|属性名		|类型		|默认值	|说明																																	|
|---			|----		|---		|---																																	|
|src			|String	|-			|图片资源地址 - 支持相对路径、绝对路径，支持 base64 码								|
|text			|String	|-			|主文案																																|
|subtext	|String	|-			|副文案																																|
|type			|String	|-			|结果页 - 默认empty，支持 页面丢失-lost 网络异常-network 无信息-empty	|
|def-btn	|String	|-			|显示普通按钮 - def-btn="普通按钮"																		|
|warn-btn	|String	|-			|显示警告按钮 - warn-btn="警告按钮"																		|
|pri-btn	|String	|-			|显示高亮按钮 - pri-btn="高亮按钮"																		|

**事件说明：**

|事件名称	|说明							|
|---			|---							|
|defBtn		|普通按钮点击事件	|
|warnBtn	|警告按钮点击事件	|
|priBtn		|高亮按钮点击事件	|
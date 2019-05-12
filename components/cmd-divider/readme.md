### Divider 分隔线

分隔线组件，组件名：``cmd-divider``，代码块： cmdDivider。

**使用方式：**

在 ``script`` 中引用组件 

```javascript
import cmdDivider from "@/components/cmd-divider/cmd-divider.vue"
export default {
    components: {cmdDivider}
}
```

用法

```html
<cmd-divider></cmd-divider>
<cmd-divider content="没有更多"></cmd-divider>
<cmd-divider content="没有更多" fontColor="#FFC82C" fontSize="25" lineColor="#78A4FA"></cmd-divider>
<cmd-divider>
  <cmd-avatar icon="add"></cmd-avatar>
</cmd-divider>
```

**属性说明：**

|属性名			|类型						|默认值	|说明										|
|---				|----						|---		|---										|
|content		|String					|-			|分隔线中间内容 - 默认无|
|height			|String, Number	|-			|分隔线高度 - 默认:60px	|
|font-color	|String					|-			|文字颜色 - 默认:#999		|
|font-size	|String					|-			|文字大小 - 默认:18px		|
|line-color	|String					|-			|线颜色 - 默认:24px			|

**事件说明：**

|事件名称	|说明									|
|---			|---									|
|click		|整个微标组件 点击事件|
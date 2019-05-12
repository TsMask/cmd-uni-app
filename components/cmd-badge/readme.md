### Badge 微标

微标组件，组件名：``cmd-badge``，代码块： cmdBadge。

**使用方式：**

在 ``script`` 中引用组件 

```javascript
import cmdBadge from "@/components/cmd-badge/cmd-badge.vue"
export default {
    components: {cmdBadge}
}
```

用法    
如果发生偏移，可以对组件内的样式进行调整

```html
<cmd-badge value="33" >
  <cmd-avatar icon="add"></cmd-avatar>
</cmd-badge>
<cmd-badge dot >
  <cmd-avatar icon="add"></cmd-avatar>
</cmd-badge>
<cmd-badge value="字符长度不大于5" >
  <cmd-avatar icon="add"></cmd-avatar>
</cmd-badge>
```

**属性说明：**

|属性名		|类型						|默认值				|说明																							|
|---			|----						|---					|---																							|
|dot			|Boolean				|false				|显示红色小圆点																		|
|value		|String, Number	|-						|显示字符数值，当长度大于5时后尾有省略号					|
|maxValue	|Number					|99						|数值最大值，对Number当数字超过时最大值+，默认99+	|
|make			|Object					|{'color': ''}|自定义微标样式 - 颜色、背景、边距等							|

**事件说明：**

|事件名称	|说明									|
|---			|---									|
|click		|整个微标组件 点击事件|

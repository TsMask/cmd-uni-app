### Curtain 幕帘

幕帘组件，组件名：``cmd-curtain``，代码块： cmdCurtain。

**使用方式：**

在 ``script`` 中引用组件 

```javascript
import cmdCurtain from "@/components/cmd-curtain/cmd-curtain.vue"
export default {
    components: {cmdCurtain}
}
```

用法

```html
cmd-curtain :visible="visible" mode="top-right">
  <image mode="aspectFit" :src="img"></image>
</cmd-curtain>
cmd-curtain :visible="visible" mode="top-let">
  <image mode="aspectFit" :src="img"></image>
</cmd-curtain>
cmd-curtain :visible="visible" mode="top">
  <image mode="aspectFit" :src="img"></image>
</cmd-curtain>
<!-- 
fnCurtain() {
  this.visible = !this.visible;
}
-->
```

**属性说明：**

|属性名	|类型		|默认值	|说明					|
|---		|----		|---		|---					|
|visible|Boolean|false	|显示幕帘层			|
|mode		|String	|bottom	|按钮方向模式	|

**mode按钮方向模式**
|按钮方向	|类型					|
|---			|----					|
|上中			|top					|
|上左			|top-left			|
|上右			|top-right		|
|下中			|bottom				|
|下左			|bottom-left	|
|下右			|bottom-right	|

**事件说明：**

|事件名称	|说明													|
|---			|---													|
|close		|幕帘打开后的关闭按钮 关闭事件|

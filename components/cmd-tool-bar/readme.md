### ToolBar 工具栏

工具栏组件，组件名：``cmd-tool-bar``，代码块： cmdToolBar。

**使用方式：**

在 ``script`` 中引用组件 

```javascript
import cmdToolBar from "@/components/cmd-tool-bar/cmd-tool-bar.vue"
export default {
    components: {cmdToolBar}
}
```

用法：    
顶部导航浮动上层，避免下方内容覆盖需要加样式    
```css
.body{
	/*距离顶部范围应该在116-120范围内*/
	padding-top: 118upx;
	top: var(--status-bar-height);
}
```

```html
<cmd-tool-bar title="标题"></cmd-tool-bar>
<cmd-tool-bar background-color="linear-gradient(to right, #12c2e9, #c471ed, #f64f59)" iconOne="menu" iconTwo="share" iconThree="reload" iconFour="help" title="基本"></cmd-tool-bar>
<cmd-tool-bar back  background-color="bule"></cmd-tool-bar>
```
 
**属性说明：**

|属性名						|类型		|默认值	|说明																	|
|---							|----		|---		|---																	|
|fixed						|Boolean|true		|工具栏固定到页面顶部									|
|back							|Boolean|false	|工具栏左侧返回按钮，默认点击返回上层	|
|title						|String	|Title	|工具栏左侧标题												|
|font-color				|String	|-			|工具栏内文字、图标的颜色							|
|background-color	|String	|-			|工具栏背景颜色												|
|icon-one					|String	|-			|工具栏图标一													|
|icon-two					|String	|-			|工具栏图标二													|
|icon-three				|String	|-			|工具栏图标三													|
|icon-four				|String	|-			|工具栏图标四													|

**事件说明：**

|事件名称	|说明									|
|---			|---									|
|iconOne	|点击 图标一 触发事件	|
|iconTwo	|点击 图标二 触发事件	|
|iconThree|点击 图标三 触发事件	|
|iconFour	|点击 图标四 触发事件	|

### NavBar 导航栏

导航栏组件，组件名：``cmd-nav-bar``，代码块： cmdNavBar。

**使用方式：**

在 ``script`` 中引用组件 

```javascript
import cmdNavBar from "@/components/cmd-nav-bar/cmd-nav-bar.vue"
export default {
    components: {cmdNavBar}
}
```

用法：    
顶部导航浮动上层，避免下方内容覆盖需要加样式    
```css
.body{
	/*距离顶部范围应该在88-95范围内*/
	padding-top: 90upx;
	top: var(--status-bar-height);
}
```

```html
<cmd-nav-bar :fixed="false" back left-text="Back" title="场景管理" iconTwo="settings" font-color="#fff" background-color="linear-gradient(to right, rgb(17, 153, 142), rgb(56, 239, 125))"></cmd-nav-bar>
<cmd-nav-bar :fixed="false" leftTitle="HELLO" iconTwo="add"></cmd-nav-bar>
<cmd-nav-bar :fixed="false" right-color="#2196f3" right-text="添加场景" back title="场景管理"></cmd-nav-bar>
<cmd-nav-bar iconOne="menu" title="基本" iconTwo="share" iconThree="reload" iconFour="help"></cmd-nav-bar>
```
 
**属性说明：**

|属性名						|类型		|默认值	|说明																														|
|---							|----		|---		|---																														|
|fixed						|Boolean|true		|导航栏固定到页面顶部 - 默认true																|
|back							|Boolean|false	|导航栏左侧返回按钮 - 默认false,点击返回上层										|
|left-text				|String	|-			|导航栏左侧文字 - 可同显导航栏左侧返回按钮											|
|left-title				|String	|-			|导航栏左侧标题 - 不可显示导航栏左侧文字、图标一、导航栏中心标题|
|title						|String	|-			|导航栏中心标题																									|
|right-text				|String	|-			|导航栏右侧文字																									|
|right-color			|String	|-			|导航栏右侧文字颜色																							|
|font-color				|String	|-			|导航栏内文字、图标的颜色																				|
|background-color	|String	|-			|导航栏背景颜色																									|
|icon-one					|String	|-			|导航栏图标一 - 不可与导航栏左侧返回按钮、导航栏左侧标题同显		|
|icon-two					|String	|-			|导航栏图标二																										|
|icon-three				|String	|-			|导航栏图标三 - 须显有导航栏图标二															|
|icon-four				|String	|-			|导航栏图标四 - 不可与导航栏右侧文字同显												|

**事件说明：**

|事件名称	|说明										|
|---			|---										|
|iconOne	|导航栏图标一 点击事件	|
|iconTwo	|导航栏图标二 点击事件	|
|iconThree|导航栏图标三 点击事件	|
|iconFour	|导航栏图标四 点击事件	|
|leftText	|导航栏左侧文字 点击事件|
|rightText|导航栏右侧文字 点击事件|

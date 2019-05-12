### BottomNav 底部导航栏

底部导航栏组件，组件名：``cmd-bottom-nav``，代码块： cmdBottomNav。

**使用方式：**

在 ``script`` 中引用组件 

```javascript
import cmdBottomNav from "@/components/cmd-bottom-nav/cmd-bottom-nav.vue"
export default {
    components: {cmdBottomNav}
}
```

用法：    
底部导航浮动上层，避免上拉后下方内容覆盖需要加样式    
```css
.body{
	/*距离顶部范围应该在118-122范围内*/
	padding-bottom: 118upx;
}
```

```html
<cmd-bottom-nav></cmd-bottom-nav>
<cmd-bottom-nav background-color="linear-gradient(to right, rgb(17, 153, 142), rgb(56, 239, 125))" :current="current" :list="list" text-auto></cmd-bottom-nav>
<cmd-bottom-nav :current="current" :list="list" border-color="red" background-color="#795548" font-color="#fff" active-font-color="rgb(255, 106, 68)"></cmd-bottom-nav>
```

```json
current: 0,
list:[{
	"pagePath": "/pages/tabbar/home/home",
	"text": "首页", 
	// 字体图标不可与图片共显
	"icon": "home",
	// src 大小限制为40kb，建议尺寸为 81px * 81px
	"src": "../../static/iocn-tabbar/home.png",
	"srcSelect": "../../static/iocn-tabbar/homeHL.png"
}]
```

**属性说明：**

|属性名				|类型	|默认值	|说明												|
|---				|----	|---	|---												|
|current			|Number	|0		|底部导航栏选中项									|
|list				|Array	|[]		|底部导航栏项列表									|
|font-color			|String	|#000	|底部导航栏文字颜色 - 默认：						|
|border-color		|String	|#dadada|底部导航栏上边线颜色								|
|background-color	|String	|#fff	|底部导航栏背景颜色									|
|active-font-color	|String	|#000	|底部导航栏激活文字颜色								|
|text-auto			|Boolean|false	|底部导航栏只在激活状态附加显示文本，默认显示图标	|
|fixed				|Boolean|true	|底部导航栏固定到页面底部							|

**事件说明：**

|事件名称	|说明						|
|---		|---						|
|click		|底部导航栏项 点击事件	|

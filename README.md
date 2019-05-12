### [cmd-uni-app组件库](http://ext.dcloud.net.cn/search?q=cmd)    

使用蓝叠模拟器演示APP、微信开发者工具演示微信小程序、猎豹浏览器演示H5。    
可以下载相关组件直接使用，具体还看真机运行效果。    
``cmd``组件写法基础，易于理解vue组件的创建使用，对于初学vue新手入uni-app友好，代码操作注释明确。    
样式修改可以通过H5方式运行后查看浏览器开发者工具，有css基础都很好理解。    
推荐新手先看看这篇[白话uni-app](http://ask.dcloud.net.cn/article/35657)    
默认使用新版编译器环境[uni-app 1.9发布，App平台升级为新版编译器（自定义组件模式），支持更多Vue语法](https://ask.dcloud.net.cn/article/35818)    

**包含组件：**    

* [头像](http://ext.dcloud.net.cn/plugin?id=176)组件名：``cmd-avatar`` 代码块： cmdAvatar
* [微标](http://ext.dcloud.net.cn/search?q=cmd)组件名：``cmd-badge`` 代码块： cmdBadge
* [列表单元](http://ext.dcloud.net.cn/plugin?id=177)组件名：``cmd-cell-item`` 代码块： cmdCellItem
* [幕帘](http://ext.dcloud.net.cn/plugin?id=179)组件名：``cmd-curtain`` 代码块： cmdCurtain
* [分隔线](http://ext.dcloud.net.cn/search?q=cmd)组件名：``cmd-divider`` 代码块： cmdDivider
* [通知栏](http://ext.dcloud.net.cn/plugin?id=178)组件名：``cmd-notice-bar`` 代码块： cmdNoticeBar
* [icon图标](http://ext.dcloud.net.cn/plugin?id=175)组件名：``cmd-icon`` 代码块： cmdIcon
* [输入框](http://ext.dcloud.net.cn/plugin?id=180)组件名：``cmd-input`` 代码块： cmdInput
* [进度条](http://ext.dcloud.net.cn/plugin?id=259)组件名：``cmd-progress`` 代码块： cmdProgress
* [结果页](http://ext.dcloud.net.cn/plugin?id=203)组件名：``cmd-result-page`` 代码块： cmdResultPage
* [底部导航栏](http://ext.dcloud.net.cn/plugin?id=188)组件名：``cmd-bottom-nav`` 代码块： cmdBottomNav
* [顶部导航栏](http://ext.dcloud.net.cn/plugin?id=199)组件名：``cmd-nav-bar`` 代码块： cmdNavBar
* [顶部工具栏](http://ext.dcloud.net.cn/plugin?id=189)组件名：``cmd-tool-bar`` 代码块： cmdToolBar
* [导航栏内容页](http://ext.dcloud.net.cn/plugin?id=207)组件名：``cmd-page-body`` 代码块： cmdPageBody    
* [动画](http://ext.dcloud.net.cn/plugin?id=211)组件名：``cmd-transition`` 代码块： cmdTransition
* [HTML 文本解析器](http://ext.dcloud.net.cn/plugin?id=263) JS库：``html-parser`` 代码块： HtmlParser

**示例模板：**
* [个人中心模板](http://ext.dcloud.net.cn/plugin?id=236)

> 以上就是所有``cmd``组件，有vue语法基础的可以快速理解学会。    
> 极大的提升vue语法进而使用``uni-app``进行开发七端应用程序。

#### 使用自定义导航栏时
```json
{
  // 全局bar样式中去除，顶部导航条、滚动条、原生回弹阴影
  "globalStyle": {
  	// 不显示工具栏toolbar
  	"navigationStyle": "custom",
  	"app-plus": {
  		// 不显示滚动条
  		"scrollIndicator": "none",
  		// 页面回弹效果
  		"bounce": "none"
  	}
  }
}
```

#### 全局样式使用    
如果``cmd``组件在使用中发生大小异常，可以在组件内加上view标签通用样式
```css
/* 全局样式 */
@import url("./common/uni/uni.css");

/* 通用 */
view {
	font-size: 28upx;
	line-height: 1.8;
}
```

#### 全局组件注册
```javasrcipt
import cmdNavBar from './components/cmd-nav-bar/cmd-nav-bar.vue'
Vue.component('cmd-nav-bar',cmdNavBar)
// 不支持用Vue.use()
```

**祝愿DCloud越做越好**
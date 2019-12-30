![北栀是条咸鱼-祝自己十九岁生日快乐](./static/157176035212071.jpg_700x.jpg)

## 起步

1. 通过 [uni-app](https://uniapp.dcloud.io/) 官网快速上手，下载HBuilderX-APP版，亲身体验下uni-app。
2. 看完 [《uni-app官方教程》](https://ke.qq.com/course/343370) ，出品人：DCloud，课时：共3节。
* 如果你熟悉h5，但不熟悉vue和小程序，建议看完这篇 [白话uni-app](http://ask.dcloud.net.cn/article/35657) 。
* `uni-app` 使用的是vue的语法，不是小程序自定义的语法，不需要专门去学习小程序的语法。
* DCloud与vue合作，在vue.js官网提供了[免费视频教程](https://learning.dcloud.io)。

> ``cmd`` 组件写法基础，易于理解`vue`组件的创建使用，对于初学vue新手入`uni-app`友好，具体还看真机运行效果。    
> 代码操作注释明确，样式修改可以通过`H5`方式运行后查看浏览器开发者工具，有`css`基础都很好理解。    

![北栀是条咸鱼-祝自己十九岁生日快乐](./static/157176035213638.jpg_700x.jpg)

## 包含组件

|组件名																										|组件名							|代码块					|说明|
|---																											|---								|---						|---|
|[通知栏组件](https://ext.dcloud.net.cn/plugin?id=178)		|``cmd-notice-bar``|cmdNoticeBar	|通常用于系统提醒、活动提醒等通知 |
|[幕帘组件](https://ext.dcloud.net.cn/plugin?id=179)			|``cmd-curtain``		|cmdCurtain		|可以用来放置广告提示内容|
|[Icon 图标组件](https://ext.dcloud.net.cn/plugin?id=175)	|``cmd-icon``				|cmdIcon			|自定义icon的封装组件|
|[列表单元组件](https://ext.dcloud.net.cn/plugin?id=177)	|``cmd-cell-item``	|cmdCellItem	|列表用于展现并列层级的信息内容|
|[结果页组件](https://ext.dcloud.net.cn/plugin?id=203)		|``cmd-result-page``|cmdResultPage			|在整张页面中向用户反馈操作结果|
|[头像组件](https://ext.dcloud.net.cn/plugin?id=176)		|``cmd-avatar``|cmdAvatar			|用于展示用户头像、数字号、单字符|
|[输入框组件](https://ext.dcloud.net.cn/plugin?id=180)		|``cmd-input``|cmdInput			|对input组件进行简单封装密码可见和清除|
|[底部导航栏组件](https://ext.dcloud.net.cn/plugin?id=188)		|``cmd-bottom-nav``|cmdBottomNav			|底部导航栏固定在页面底部|
|[导航栏内容页组件](https://ext.dcloud.net.cn/plugin?id=207)		|``cmd-page-body``|cmdPageBody			|针对使用底部导航栏或顶部导航栏->废弃|
|[动画组件](https://ext.dcloud.net.cn/plugin?id=211)		|``cmd-transition``|cmdTransition			|复用动画切换|
|[工具栏组件](https://ext.dcloud.net.cn/plugin?id=189)		|``cmd-tool-bar``|cmdToolBar			|工具栏是安卓md风格的，标题加图标|
|[导航栏组件](https://ext.dcloud.net.cn/plugin?id=199)		|``cmd-nav-bar``|cmdNavBar			|简单封装自定义导航栏|
|[进度圈组件](https://ext.dcloud.net.cn/plugin?id=965)		|``cmd-circle``|cmdCircle			|用圈显示一个操作完成的百分比时|
|[进度条组件](https://ext.dcloud.net.cn/plugin?id=259)		|``cmd-progress``|cmdProgress			|为用户显示该操作的当前进度和状态|
       
|JS SDK																											|SDK名					|代码块				|说明																	|
|---																												|---						|---					|---																	|
|[HTML 文本解析器](https://ext.dcloud.net.cn/plugin?id=263)	|``html-parser``|  HtmlParser	|用于解析text文本，通过DOM方式获取节点|

**全局组件注册**
```javasrcipt
// main.js
import cmdNavBar from './components/cmd-nav-bar/cmd-nav-bar.vue'
Vue.component('cmd-nav-bar',cmdNavBar) // 不支持用Vue.use()
```
> 以上就是所有 ``cmd`` 组件，有vue语法基础的可以快速理解学会。    
> 极大的提升vue语法进而使用 ``uni-app`` 进行开发七端应用程序。    
> 本人 [插件市场发布](https://ext.dcloud.net.cn/search?q=cmd) 列表

## 示例模板 - [个人中心模板](https://ext.dcloud.net.cn/plugin?id=236)

## 祝愿DCloud越做越好
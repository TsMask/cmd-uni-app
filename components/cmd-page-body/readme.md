### PageBody 导航栏内容页

导航栏内容页组件，组件名：``cmd-page-body``，代码块： cmdPageBody。

**使用方式：**

在 ``script`` 中引用组件 

```javascript
import cmdPageBody from "@/components/cmd-page-body/cmd-page-body.vue"
export default {
    components: {cmdPageBody}
}
```

**用法**  
针对使用底部导航栏组件``cmd-bottom-nav``或顶部导航栏组件``cmd-nav-bar``时。    
内容区默认充满屏幕。    
内容区可以配合动画``cmd-transition``使用过渡动画效果减少页面的闪烁。    

```html
<cmd-nav-bar :title="顶部导航栏"></cmd-nav-bar>
<!-- 在使用顶部和底部导航栏时,top-bottom -->
<cmd-page-body type="top-bottom">
  <!-- #ifdef H5 -->
  <cmd-transition name="fade-up">
    <home v-if="current == 0"></home>
    <person v-if="current == 1"></person>
  </cmd-transition>
  <!-- #endif -->
  <!-- 单使用顶部导航时，非H5端下v-if显示，可以在mounted后 -->
  <!-- #ifndef H5 -->
  <cmd-transition v-if="current == 0" name="fade-up">
    <home></home>
  </cmd-transition>
  <cmd-transition v-if="current == 1" name="fade-up">
    <person></person>
  </cmd-transition>
  <!-- #endif -->
</cmd-page-body>
<!-- 底部导航栏 -->
<cmd-bottom-nav @click="getBottomNavCurrent" :current="current" :list="list"></cmd-bottom-nav>
```
 
**属性说明：**

|属性名						|类型		|默认值	|说明																		|
|---							|----		|---		|---																		|
|type							|String	|top		|使用导航栏类型：top、bottom、top-bottom|
|background-color	|String	|#ffffff|内容区背景颜色													|


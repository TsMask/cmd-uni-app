### LoadMore 加载更多

加载更多组件，组件名：``cmd-load-more``，代码块： cmdLoadMore。

**使用方式：**

在 ``script`` 中引用组件 

```javascript
import cmdLoadMore from "@/components/cmd-load-more/cmd-load-more.vue"
export default {
    components: {cmdLoadMore}
}
```

用法    
```html
<!-- 待加载 -->
<cmd-load-more :status="0" color="#654321"></cmd-load-more>
<!-- 加载中 -->
<cmd-load-more :status="1" color="#654321"></cmd-load-more>
<!-- 无数据 -->
<cmd-load-more :status="-1" color="#654321"></cmd-load-more>
```
 
**属性说明：**

|属性名	|类型		|默认值	|说明																	|
|---		|----		|---		|---																	|
|color	|String	|#999		|图标和文字颜色												|
|status	|Number	|0			|加载状态 - 待加载0、加载中1、无数据-1|


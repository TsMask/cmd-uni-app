### Progress 进度条

进度条组件，组件名：``cmd-progress``，代码块： cmdProgress。

**使用方式：**

在 ``script`` 中引用组件 

```javascript
import cmdProgress from "@/components/cmd-progress/cmd-progress.vue"
export default {
    components: {cmdProgress}
}
```

用法：   
**非H5端动态绘制会有卡顿情况，H5端没有。**    
**非H5端使用image/svg+xml背景方式，H5端正常使用svg。**    
**正常使用自定义组件模式和非自定义组件模式。**    
如果需要快速大量动态加载的可以考虑用
[wx-charts轻量级跨全端图表]("https://ext.dcloud.net.cn/plugin?id=271"),
小量初始数据用这种简单易改的小组件就行啦    

```html
<!-- 进度条 --> 
<cmd-progress :percent="30"></cmd-progress>
<cmd-progress :percent="59" :success-percent="10"></cmd-progress>
<cmd-progress :percent="50" :showInfo="false"></cmd-progress>
<cmd-progress :percent="80" status="active"></cmd-progress>
<cmd-progress :percent="50" status="success"></cmd-progress>
<cmd-progress :percent="70" status="exception"></cmd-progress>
<cmd-progress :percent="25" :stroke-width="24"></cmd-progress>
<cmd-progress :percent="68" stroke-color="linear-gradient(to right, #ef32d9, #89fffd)"></cmd-progress>
<cmd-progress :percent="88" stroke-shape="square"></cmd-progress>
<!-- 进度圈 -->
<cmd-progress type="circle" :percent="75"></cmd-progress>
<cmd-progress type="circle" :percent="75" :showInfo="false"></cmd-progress>
<cmd-progress type="circle" :percent="30" status="exception"></cmd-progress>
<cmd-progress type="circle" :percent="60" status="success"></cmd-progress>
<cmd-progress type="circle" :percent="0"></cmd-progress>
<cmd-progress type="circle" :percent="76" :stroke-width="24"></cmd-progress>
<cmd-progress type="circle" :percent="45" :gapDegree="66" stroke-color="#ef32d9"></cmd-progress>
<cmd-progress type="circle" :percent="88" gap-position="left" stroke-shape="square"></cmd-progress>
<cmd-progress type="circle" :percent="76" :width="40" stroke-shape="square"></cmd-progress>
<!-- 仪表盘 -->
<cmd-progress type="dashboard" :percent="75"></cmd-progress>
<cmd-progress type="dashboard" :percent="68" status="exception"></cmd-progress>
<cmd-progress type="dashboard" :percent="88" status="success"></cmd-progress>
<cmd-progress type="dashboard" :percent="43" :stroke-width="24"></cmd-progress>
<cmd-progress type="dashboard" :percent="30" stroke-color="#ef32d9"></cmd-progress>
<cmd-progress type="dashboard" :percent="34" stroke-shape="square"></cmd-progress>
```
 
**属性说明：**

|属性名			|类型	|默认值	|说明																										|
|---			|----	|---	|---																										|
|type			|String	|line	|进度类型 - 线型：line、圆圈形：circle、仪表盘：dashboard，默认线型：line									|
|percent		|Number	|0		|进度百分比值 - 显示范围0-100 ，可能数比较大就需要自己转成百分比的值										|
|success-percent|Number	|0		|进度已完成的百分几 - 仅支持进度线型：line																	|
|status			|String	|normal	|进度状态 - 涌动：active（仅支持线型：line）、正常：normal、完成：success、失败：exception，默认正常：normal|
|show-info		|Boolean|true	|进度状态信息 - 是否显示进度数值或状态图标，默认true														|
|stroke-width	|Number	|6		|进度线条的宽度 - 建议在条线的宽度范围：1-50，与进度条显示宽度有关，默认8									|
|stroke-color	|String	|-		|进度线条的颜色 - 渐变色仅支持线型：line																	|
|stroke-shape	|String	|round	|进度线条两端的形状 - 圆：round、方块直角：square，默认圆：round											|
|width			|Number	|80		|进度画布宽度 - 仅支持圆圈形：circle、仪表盘：dashboard，默认80												|
|gap-degree		|Number	|0		|进度圆形缺口角度 - 可取值 0 ~ 360,仅支持圆圈形：circle、仪表盘：dashboard									|
|gap-position	|String	|top	|进度圆形缺口位置 - 可取值'top', 'bottom', 'left', 'right',仅支持圆圈形：circle、仪表盘：dashboard			|

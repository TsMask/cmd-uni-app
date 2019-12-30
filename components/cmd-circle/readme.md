### Circle 进度圈

进度圈组件，组件名：``cmd-circle``，代码块： cmdCircle。

**使用方式：**

在 ``script`` 中引用组件 

```javascript
import cmdCircle from "@/components/cmd-circle/cmd-circle.vue"
export default {
    components: {cmdCircle}
}
```

用法：    
使用canvas基础圈绘制，实现圆弧进度图、仪表盘功能    
代码注释完整，结构清晰，尽可能自定义    
非H5端正常绘制无卡顿，H5端只要动态值才显示有卡顿    
更多需求功能图表实现，请使用[uCharts高性能跨全端图表](https://ext.dcloud.net.cn/plugin?id=271), 

```html
<view>进度圈</view>
<cmd-circle cid="circle10" type="circle" :percent="56"></cmd-circle>
<cmd-circle cid="circle11" type="circle" :percent="75" :showInfo="false"></cmd-circle>
<cmd-circle cid="circle12" type="circle" :percent="30" status="exception"></cmd-circle>
<cmd-circle cid="circle13" type="circle" :percent="89" status="success"></cmd-circle>
<cmd-circle cid="circle14" type="circle" :percent="45" font-color="#ff9800" :font-size="18"></cmd-circle>
<cmd-circle cid="circle15" type="circle" :percent="68" font-color="#cddc39" :font-size="12" stroke-width="12" stroke-color="#9c27b0"></cmd-circle>
<cmd-circle cid="circle16" type="circle" :percent="34" font-color="#cddc39" :font-size="5" width="40" stroke-width="5" stroke-shape="round" stroke-color="#ff5722" stroke-background="#607d8b"></cmd-circle>
<cmd-circle cid="circle17" type="circle" :percent="73" font-color="#cddc39" :font-size="14" width="150" stroke-width="24" stroke-shape="round" stroke-color="#fde16d" stroke-background="#795548" gap-degree="300" gap-position="left"></cmd-circle>
<view>仪表盘</view>
<cmd-circle cid="circle30" type="dashboard" :percent="56"></cmd-circle>
<cmd-circle cid="circle31" type="dashboard" :percent="75" :showInfo="false"></cmd-circle>
<cmd-circle cid="circle32" type="dashboard" :percent="30" status="exception"></cmd-circle>
<cmd-circle cid="circle33" type="dashboard" :percent="89" status="success"></cmd-circle>
<cmd-circle cid="circle34" type="dashboard" :percent="45" font-color="#ff9800" :font-size="18"></cmd-circle>
<cmd-circle cid="circle35" type="dashboard" :percent="68" font-color="#cddc39" :font-size="12" stroke-width="12" stroke-color="#9c27b0"></cmd-circle>
<cmd-circle cid="circle36" type="dashboard" :percent="34" font-color="#cddc39" :font-size="5" width="40" stroke-width="5" stroke-shape="round" stroke-color="#ff5722" stroke-background="#607d8b"></cmd-circle>
<cmd-circle cid="circle37" type="dashboard" :percent="78" font-color="#cddc39" :font-size="16" width="150" stroke-width="24" stroke-shape="round" stroke-color="#fde16d" stroke-background="#607d8b"></cmd-circle>
<view>动态值</view>
<cmd-circle cid="circle18" type="circle" :percent="p" font-color="#607d8b" :font-size="24" width="150" stroke-width="18" stroke-shape="square" stroke-color="#f44336" stroke-background="#9c27b0"></cmd-circle>
<cmd-circle cid="circle38" type="dashboard" :percent="p" font-color="#607d8b" :font-size="18" width="150" stroke-width="24" stroke-shape="round" stroke-color="#009688" stroke-background="#8bc34a"></cmd-circle>
<view>自定圈信息格式</view>
<view style="display: flex;justify-content: center;position: relative;background: #f3f3f3;height: 360rpx;overflow: hidden;">
  <cmd-circle cid="circle19" type="circle" :percent="3 /20 * 100" :showInfo="false" width="180" stroke-width="14" stroke-shape="round" stroke-color="#009688" stroke-background="#9e9e9e"></cmd-circle>
  <view style="position: absolute;text-align: center;top: 25%;">
    <view style="font-size: 28rpx;">已使用/GB</view>
    <view style="font-size: 42rpx;font-weight: bold;padding-bottom: 28rpx;">3.33GB</view>
    <view style="font-size: 28rpx;">总流量畅享</view>
  </view>
</view>
<view style="display: flex;justify-content: center;position: relative;height: 360rpx;overflow: hidden;">
  <cmd-circle cid="circle39" type="dashboard" :percent="19.45 /20 * 100" :showInfo="false" width="200" stroke-width="14" stroke-shape="round" stroke-color="#ff9800" stroke-background="#f5f5f5"></cmd-circle>
  <view style="position: absolute;text-align: center;top: 30%;">
    <view style="font-size: 32rpx;">亲，流量告急</view>
    <view style="font-size: 64rpx;font-weight: bold;">19.45</view>
    <view style="font-size: 36rpx;">GB</view>
  </view>
</view>
```
 
**属性说明：**

|属性名						|类型		|默认值				|说明																																					|
|---							|----		|---					|---																																					|
|cid							|String	|defaultCanvas|画布编号																																			|
|type							|String	|circle				|进度圈类型 - 圆圈形：circle、仪表盘：dashboard																|
|percent					|Number	|0						|进度圈百分比值 - 显示范围0-100 ，可能数比较大就需要自己转成百分比的值				|
|show-info				|Boolean|true					|进度圈进度状态信息 - 显示进度数值或状态																			|
|font-color				|String	|#595959			|进度圈文字信息颜色																														|
|font-size				|Number	|14						|进度圈文字信息大小																														|
|status						|String	|normal				|进度圈状态 - 正常：normal、完成：success、失败：exception										|
|stroke-width			|Number	|6						|进度圈线条宽度 - 建议在条线的宽度范围：1-50，与进度条显示宽度有关						|
|stroke-color			|String	|							|进度圈的颜色 - 改变status状态无效																						|
|stroke-background|String	|#eeeeee			|进度圈的底圈颜色																															|
|stroke-shape			|String	|round				|进度圈两端的形状 - 圆：round、方直角：square																	|
|width						|Number	|80						|进度圈布宽度																																	|
|gap-degree				|Number	|0						|进度圈形缺口角度 - 可取值 0 ~ 360，仅支持类型：circle												|
|gap-position			|String	|top					|进度圈形缺口位置 - 可取值'top', 'bottom', 'left', 'right'，仅支持类型：circle|
 
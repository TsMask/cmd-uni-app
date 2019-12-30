<template>
  <view> 
    <view>进度圈</view>
    <cmd-circle cid="circle10" type="circle" :percent="56"></cmd-circle>
    <cmd-circle cid="circle11" type="circle" :percent="75" :showInfo="false"></cmd-circle>
    <cmd-circle cid="circle12" type="circle" :percent="30" status="exception"></cmd-circle>
    <cmd-circle cid="circle13" type="circle" :percent="89" status="success"></cmd-circle>
    <cmd-circle cid="circle14" type="circle" :percent="45" font-color="#ff9800" :font-size="18"></cmd-circle>
    <cmd-circle cid="circle15" type="circle" :percent="68" font-color="#cddc39" :font-size="12" :stroke-width="12" stroke-color="#9c27b0"></cmd-circle>
    <cmd-circle cid="circle16" type="circle" :percent="34" font-color="#cddc39" :font-size="5" :width="40" :stroke-width="5" stroke-shape="round" stroke-color="#ff5722" stroke-background="#607d8b"></cmd-circle>
    <cmd-circle cid="circle17" type="circle" :percent="73" font-color="#cddc39" :font-size="14" :width="150" :stroke-width="24" stroke-shape="round" stroke-color="#fde16d" stroke-background="#795548" :gap-degree="300" gap-position="left"></cmd-circle>
    <view>仪表盘</view>
    <cmd-circle cid="circle30" type="dashboard" :percent="56"></cmd-circle>
    <cmd-circle cid="circle31" type="dashboard" :percent="75" :showInfo="false"></cmd-circle>
    <cmd-circle cid="circle32" type="dashboard" :percent="30" status="exception"></cmd-circle>
    <cmd-circle cid="circle33" type="dashboard" :percent="89" status="success"></cmd-circle>
    <cmd-circle cid="circle34" type="dashboard" :percent="45" font-color="#ff9800" :font-size="18"></cmd-circle>
    <cmd-circle cid="circle35" type="dashboard" :percent="68" font-color="#cddc39" :font-size="12" :stroke-width="12" stroke-color="#9c27b0"></cmd-circle>
    <cmd-circle cid="circle36" type="dashboard" :percent="34" font-color="#cddc39" :font-size="5" :width="40" :stroke-width="5" stroke-shape="round" stroke-color="#ff5722" stroke-background="#607d8b"></cmd-circle>
    <cmd-circle cid="circle37" type="dashboard" :percent="78" font-color="#cddc39" :font-size="16" :width="150" :stroke-width="24" stroke-shape="round" stroke-color="#fde16d" stroke-background="#607d8b"></cmd-circle>
    <view>动态值</view>
    <cmd-circle cid="circle18" type="circle" :percent="p" font-color="#607d8b" :font-size="24" :width="150" :stroke-width="18" stroke-shape="square" stroke-color="#f44336" stroke-background="#9c27b0"></cmd-circle>
    <cmd-circle cid="circle38" type="dashboard" :percent="p" font-color="#607d8b" :font-size="18" :width="150" :stroke-width="24" stroke-shape="round" stroke-color="#009688" stroke-background="#8bc34a"></cmd-circle>
    <view>自定圈信息格式</view>
    <view style="display: flex;justify-content: center;position: relative;background: #f3f3f3;height: 360rpx;overflow: hidden;">
      <cmd-circle cid="circle19" type="circle" :percent="3 /20 * 100" :showInfo="false" :width="180" :stroke-width="14" stroke-shape="round" stroke-color="#009688" stroke-background="#9e9e9e"></cmd-circle>
      <view style="position: absolute;text-align: center;top: 25%;">
        <view style="font-size: 28rpx;">已使用/GB</view>
        <view style="font-size: 42rpx;font-weight: bold;padding-bottom: 28rpx;">3.33GB</view>
        <view style="font-size: 28rpx;">总流量畅享</view>
      </view>
    </view>
    <view style="display: flex;justify-content: center;position: relative;height: 360rpx;overflow: hidden;">
      <cmd-circle cid="circle39" type="dashboard" :percent="19.45 /20 * 100" :showInfo="false" :width="200" :stroke-width="14" stroke-shape="round" stroke-color="#ff9800" stroke-background="#f5f5f5"></cmd-circle>
      <view style="position: absolute;text-align: center;top: 30%;">
        <view style="font-size: 32rpx;">亲，流量告急</view>
        <view style="font-size: 64rpx;font-weight: bold;">19.45</view>
        <view style="font-size: 36rpx;">GB</view>
      </view>
    </view> 
  </view>
</template>

<script>
  import cmdCircle from '@/components/cmd-circle/cmd-circle.vue'
  export default {
    components: {
      cmdCircle
    },
    data() {
      return {
        p: 0,
        inter: null
      };
    },
    mounted() {
      this.inter = setInterval(() => {
        this.p++;
        if (this.p >= 120) {
          this.p = 0;
          // clearInterval(inter)
        }
      }, 300)
    },
    onUnload() {
      clearInterval(this.inter)
    }
  }
</script>

<style>
</style>

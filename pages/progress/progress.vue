<template>
  <view>
    <view class="">进度条</view>
    <cmd-progress :percent="30"></cmd-progress>
    <cmd-progress :percent="100"></cmd-progress>
    <cmd-progress :percent="16" :success-percent="10"></cmd-progress>
    <cmd-progress :percent="0"></cmd-progress>
    <cmd-progress :percent="50" :showInfo="false"></cmd-progress>
    <cmd-progress :percent="80" status="active"></cmd-progress>
    <cmd-progress :percent="50" status="success"></cmd-progress>
    <cmd-progress :percent="70" status="exception"></cmd-progress>
    <cmd-progress :percent="25" :stroke-width="24"></cmd-progress>
    <cmd-progress :percent="68" stroke-color="linear-gradient(to right, #ef32d9, #89fffd)"></cmd-progress>
    <cmd-progress :percent="88" stroke-shape="square"></cmd-progress>
    <cmd-progress :percent="p" :success-percent="sp" :stroke-width="12" status="active"></cmd-progress>
    <view>进度圈</view>
    <cmd-progress type="circle" :percent="75"></cmd-progress>
    <cmd-progress type="circle" :percent="75" :showInfo="false"></cmd-progress>
    <cmd-progress type="circle" :percent="30" status="exception"></cmd-progress>
    <cmd-progress type="circle" :percent="60" status="success"></cmd-progress>
    <cmd-progress type="circle" :percent="0"></cmd-progress>
    <cmd-progress type="circle" :percent="76" :stroke-width="24"></cmd-progress>
    <cmd-progress type="circle" :percent="45" :gapDegree="66" stroke-color="#ef32d9"></cmd-progress>
    <cmd-progress type="circle" :percent="88" gap-position="left" stroke-shape="square"></cmd-progress>
    <cmd-progress type="circle" :percent="76" :width="40" stroke-shape="square"></cmd-progress>
    <cmd-progress type="circle" :percent="p" :stroke-width="12"></cmd-progress>
    <view>仪表盘</view>
    <cmd-progress type="dashboard" :percent="75"></cmd-progress>
    <cmd-progress type="dashboard" :percent="68" status="exception"></cmd-progress>
    <cmd-progress type="dashboard" :percent="88" status="success"></cmd-progress>
    <cmd-progress type="dashboard" :percent="43" :stroke-width="24"></cmd-progress>
    <cmd-progress type="dashboard" :percent="30" stroke-color="#ef32d9"></cmd-progress>
    <cmd-progress type="dashboard" :percent="34" stroke-shape="square"></cmd-progress>
    <cmd-progress type="dashboard" :percent="p" :stroke-width="12"></cmd-progress>
    <view>自定义格式</view>
    <view style="display: flex;justify-content: center;position: relative;background: #f3f3f3;">
      <cmd-progress type="dashboard" :percent="19.23 / 20 * 100" stroke-color="#ff9800" :stroke-width="8" :width="250" stroke-shape="square" :showInfo="false"></cmd-progress>
      <view style="position: absolute;text-align: center;top: 30%;">
        <view style="font-size:36rpx;">亲，流量告急</view>
        <view style="font-size:72rpx;font-weight: bold;">19.23</view>
        <view style="font-size:32rpx;">MB</view>
      </view>
    </view>
    <view style="display: flex;justify-content: center;position: relative;">
      <cmd-progress type="circle" :percent="3.33/ 20 * 100" stroke-color="#009688" :stroke-width="12" :width="250" :showInfo="false"></cmd-progress>
      <view style="position: absolute;text-align: center;top: 30%;">
        <view style="font-size:36rpx;">已使用/GB</view>
        <view style="font-size:72rpx;font-weight: bold;line-height: 1;padding-bottom: 28rpx;">3.33</view>
        <view style="font-size:32rpx;">总流量畅享</view>
      </view>
    </view>
  </view>
</template>

<script>
  import cmdProgress from '@/components/cmd-progress/cmd-progress.vue'
  export default {
    components: {
      cmdProgress
    },
    data() {
      return {
        p: 0,
        sp: 0,
        inter: null
      };
    },
    mounted() {
      this.inter = setInterval(() => {
        this.p++;
        this.sp = this.p + Math.random() - 20;
        if (this.p >= 100) {
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

<template>
  <view class="cmd-load-more">
    <view class="cmd-load-more-img" v-if="status === 1">
      <view class="load1">
        <view :style="{background:color}"></view>
        <view :style="{background:color}"></view>
        <view :style="{background:color}"></view>
        <view :style="{background:color}"></view>
      </view>
      <view class="load2">
        <view :style="{background:color}"></view>
        <view :style="{background:color}"></view>
        <view :style="{background:color}"></view>
        <view :style="{background:color}"></view>
      </view>
      <view class="load3">
        <view :style="{background:color}"></view>
        <view :style="{background:color}"></view>
        <view :style="{background:color}"></view>
        <view :style="{background:color}"></view>
      </view>
    </view>
    <text class="cmd-load-more-text" :style="{color:color}">{{status === 0 ? '上拉显示更多' : (status === 1 ? '正在加载...' : '没有更多数据了')}}</text>
  </view>
</template>

<script>
  /**  
   * 加载更多状态组件  
   * @description 用于上拉显示状态文字提醒。  
   * @tutorial http://ext.dcloud.net.cn/search?q=cmd  
   * @property {String} color 图标和文字颜色 - 默认：#999  
   * @property {Number} status 加载状态 - 待加载0、加载中1、无数据-1  
   * @example <cmd-load-more :status="1" color="#654321"></cmd-load-more>  
   */
  export default {
    name: 'cmd-load-more',

    props: {
      /**
       * 加载显示的文字icon颜色
       */
      color: {
        type: String,
        default: '#999'
      },
      /**
       * 加载状态，待加载0、加载中1、无数据-1
       */
      status: {
        type: Number,
        default: 0
      }
    }

  }
</script>

<style>
  .cmd-load-more {
    display: flex;
    flex-direction: row;
    height: 80upx;
    align-items: center;
    justify-content: center;
  }

  .cmd-load-more-text {
    font-size: 28upx;
    color: #999;
  }

  .cmd-load-more-img {
    height: 24px;
    width: 24px;
    margin-right: 10px;
  }

  .cmd-load-more-img>view {
    position: absolute;
  }

  .cmd-load-more-img>view view {
    width: 6px;
    height: 2px;
    border-top-left-radius: 1px;
    border-bottom-left-radius: 1px;
    background: #999;
    position: absolute;
    opacity: 0.2;
    transform-origin: 50%;
    animation: load 1.56s ease infinite;
  }

  .cmd-load-more-img>view view:nth-child(1) {
    transform: rotate(90deg);
    top: 2px;
    left: 9px;
  }

  .cmd-load-more-img>view view:nth-child(2) {
    transform: rotate(180deg);
    top: 11px;
    right: 0px;
  }

  .cmd-load-more-img>view view:nth-child(3) {
    transform: rotate(270deg);
    bottom: 2px;
    left: 9px;
  }

  .cmd-load-more-img>view view:nth-child(4) {
    top: 11px;
    left: 0px;
  }

  .load1,
  .load2,
  .load3 {
    height: 24px;
    width: 24px;
  }

  .load2 {
    transform: rotate(30deg);
  }

  .load3 {
    transform: rotate(60deg);
  }

  .load1 view:nth-child(1) {
    animation-delay: 0s;
  }

  .load2 view:nth-child(1) {
    animation-delay: 0.13s;
  }

  .load3 view:nth-child(1) {
    animation-delay: 0.26s;
  }

  .load1 view:nth-child(2) {
    animation-delay: 0.39s;
  }

  .load2 view:nth-child(2) {
    animation-delay: 0.52s;
  }

  .load3 view:nth-child(2) {
    animation-delay: 0.65s;
  }

  .load1 view:nth-child(3) {
    animation-delay: 0.78s;
  }

  .load2 view:nth-child(3) {
    animation-delay: 0.91s;
  }

  .load3 view:nth-child(3) {
    animation-delay: 1.04s;
  }

  .load1 view:nth-child(4) {
    animation-delay: 1.17s;
  }

  .load2 view:nth-child(4) {
    animation-delay: 1.3s;
  }

  .load3 view:nth-child(4) {
    animation-delay: 1.43s;
  }

  @-webkit-keyframes load {
    0% {
      opacity: 1;
    }

    100% {
      opacity: 0.2;
    }
  }
</style>

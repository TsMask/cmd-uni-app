<template>
  <view>
    <view class="">
      cmd-notice-bar
    </view>
    <view class="">
      单行多行
    </view>
    <cmd-notice-bar text="为了确保您的资金安全，请设置支付密码"></cmd-notice-bar>
    <cmd-notice-bar rows text="为了确保您的资金安全，请设置支付密码。为了确保您的资金安全，请设置支付密码。为了确保您的资金安全，请设置支付密码."></cmd-notice-bar>
    <view class="">
      显示图标、情景色、圆角
    </view>
    <cmd-notice-bar text="为了确保您的资金安全，请设置支付密码" type="activity" icon="alert-circle"></cmd-notice-bar>
    <cmd-notice-bar text="为了确保您的资金安全，请设置支付密码" type="warning" mode="link"></cmd-notice-bar>
    <cmd-notice-bar text="为了确保您的资金安全，请设置支付密码" :round="true" mode="closable"></cmd-notice-bar>
    <view class="">
      文字滚动
    </view>
    <cmd-notice-bar scrollable text="为了确保您的资金安全，请设置支付密码。为了确保您的资金安全，请设置支付密码。为了确保您的资金安全，请设置支付密码."></cmd-notice-bar>
    <view class="">
      自动关闭
    </view>
    <cmd-notice-bar :time="5000" icon="alert-circle" scrollable text="为了确保您的资金安全，请设置支付密码。为了确保您的资金安全，请设置支付密码。为了确保您的资金安全，请设置支付密码."></cmd-notice-bar>
    <cmd-notice-bar mode="link" @link="fnClickLink" icon="alert-circle" scrollable text="为了确保您的资金安全，请设置支付密码。为了确保您的资金安全，请设置支付密码。为了确保您的资金安全，请设置支付密码."></cmd-notice-bar>
    <cmd-notice-bar mode="close" @close="fnClickClose" icon="alert-circle" scrollable text="为了确保您的资金安全，请设置支付密码。为了确保您的资金安全，请设置支付密码。为了确保您的资金安全，请设置支付密码."></cmd-notice-bar>

  </view>
</template>

<script>
  import cmdNoticeBar from "@/components/cmd-notice-bar/cmd-notice-bar.vue"
  export default {
    components: {
      cmdNoticeBar
    },
    data() {
      return {};
    },
    methods: {
      fnClickLink(e) {
        console.log('点击跳转链接', e);
      },
      fnClickClose(e) {
        console.log('点击关闭', e);
      }
    }
  }
</script>

<style>

</style>

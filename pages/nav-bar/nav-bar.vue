<template>
  <view>
    <cmd-nav-bar back left-text="Back" title="场景管理" iconTwo="settings" font-color="#fff" background-color="linear-gradient(to right, rgb(17, 153, 142), rgb(56, 239, 125))"></cmd-nav-bar>

    <view class="cmd-page-body">
      <view class="" style="background: #efefef;">
        -----
      </view>
      <cmd-nav-bar :fixed="false" leftTitle="HELLO" iconTwo="add"></cmd-nav-bar>
      <view class="" style="background: #efefef;">
        ----
      </view>
      <cmd-nav-bar :fixed="false" right-color="#2196f3" right-text="添加场景" back title="场景管理"></cmd-nav-bar>
      <view class="" style="background: #efefef;">
        -----
      </view>
      <cmd-nav-bar :fixed="false" iconOne="menu" title="基本" iconTwo="share" iconThree="reload" iconFour="help"></cmd-nav-bar>
      <view class="" style="background: #efefef;">
        -----
      </view>
      <view v-for="i in 99" :key="i">
        cmdNavBar - {{i}}
      </view>
    </view>
  </view>
</template>

<script>
  import cmdNavBar from "@/components/cmd-nav-bar/cmd-nav-bar.vue"
  export default {
    components: {
      cmdNavBar
    },
    data() {
      return {

      };
    }
  }
</script>

<style>
  .cmd-page-body {
    padding-top: 90upx;
    margin-top: var(--status-bar-height);
  }
</style>

<template>
  <view>
    <cmd-tool-bar background-color="linear-gradient(to right, #12c2e9, #c471ed, #f64f59)" back iconOne="menu"
      iconTwo="share" iconThree="reload" iconFour="help" title="基本"></cmd-tool-bar>
    <view class="cmd-page-body">
      <view v-for="i in 99" :key="i">
        toolbar - {{i}}
      </view>
    </view>

  </view>
  </view>
</template>

<script>
  import cmdToolBar from "@/components/cmd-tool-bar/cmd-tool-bar.vue"
  export default {
    components: {
      cmdToolBar
    },
    data() {
      return {

      };
    }
  }
</script>

<style>
  .cmd-page-body {
    padding-top: 114upx;
    margin-top: var(--status-bar-height);
  }
</style>

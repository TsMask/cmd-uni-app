<script>
  export default {
    onLaunch() {
      console.log('App Launch');
      // #ifdef APP-PLUS
      // 锁定屏幕方向
      plus.screen.lockOrientation('portrait-primary'); //锁定
      // #endif
    },
    onShow() {
      console.log('App Show');
    },
    onHide() {
      console.log('App Hide');
    }
  }
</script>

<style>
  /* 全局样式 */
  @import url("./common/uni/uni.css");
  @import url("./common/anticon/iconfont.css");
</style>

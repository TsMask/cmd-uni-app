<template>
  <view>
    <view style="background: #f5f5f5;">
      默认
    </view>
    <cmd-result-page></cmd-result-page>
    <view style="background: #f5f5f5;">
      页面丢失
    </view>
    <cmd-result-page type="lost"></cmd-result-page>
    <view style="background: #f5f5f5;">
      网络异常
    </view>
    <cmd-result-page type="network"></cmd-result-page>
    <view style="background: #f5f5f5;">
      按钮列表
    </view>
    <cmd-result-page type="lost" 
    def-btn="返回" @defBtn="fnClick('defbtn')" 
    pri-btn="再来一次" @priBtn="fnClick('pribtn')" 
    warn-btn="终止" @warnBtn="fnClick('warnbtn')"></cmd-result-page>
    <view style="background: #f5f5f5;">
      自定义图案
    </view>
    <cmd-result-page src="https://gw.alipayobjects.com/zos/rmsportal/HWuSTipkjJRfTWekgTUG.svg" text="等待处理" subtext="已提交申请，等待银行处理"></cmd-result-page>

  </view>
</template>

<script>
  import cmdResultPage from "@/components/cmd-result-page/cmd-result-page.vue"
  export default {
    components: {
      cmdResultPage
    },
    data() {
      return {};
    },
    methods: {
      fnClick(type) {
        if (type == 'pribtn') {
          console.log('推荐操作');
        }
        if (type == 'warnbtn') {
          console.log('警告操作');
        }
        if (type == 'defbtn') {
          console.log('默认操作');
        }
      }
    }
  }
</script>

<style>

</style>

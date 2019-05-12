<template>
  <view>
    <view class="">
      分隔线divider
    </view>

    <cmd-divider></cmd-divider>
    <cmd-divider content="没有更多" @click="fnClick"></cmd-divider>
    <cmd-divider content="没有更多" fontColor="#FFC82C" fontSize="25" lineColor="#78A4FA"></cmd-divider>
    <cmd-divider>
      <cmd-avatar icon="add"></cmd-avatar>
    </cmd-divider>

  </view>
</template>

<script>
  import cmdDivider from "@/components/cmd-divider/cmd-divider.vue"
  import cmdAvatar from "@/components/cmd-avatar/cmd-avatar.vue"
  export default {
    components: {
      cmdDivider,
      cmdAvatar
    },
    data() {
      return {

      };
    },
    methods: {
      fnClick(e) {
        console.log(e)
      }
    }
  }
</script>

<style>

</style>

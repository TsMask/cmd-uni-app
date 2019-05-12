<template>
  <view>
    <!-- #ifdef H5 -->
    <cmd-transition name="fade">
      <view v-if="show">你好，uni-app</view>
    </cmd-transition>
    <cmd-transition name="fade-up">
      <view v-if="show">你好，uni-app</view>
    </cmd-transition>
    <cmd-transition name="fade-down">
      <view v-if="show">你好，uni-app</view>
    </cmd-transition>
    <cmd-transition name="fade-left">
      <view v-if="show">你好，uni-app</view>
    </cmd-transition>
    <cmd-transition name="fade-right">
      <view v-if="show">你好，uni-app</view>
    </cmd-transition>
    <cmd-transition name="slide-up">
      <view v-if="show">你好，uni-app</view>
    </cmd-transition>
    <cmd-transition name="slide-down">
      <view v-if="show">你好，uni-app</view>
    </cmd-transition>
    <cmd-transition name="slide-left">
      <view v-if="show">你好，uni-app</view>
    </cmd-transition>
    <cmd-transition name="slide-right">
      <view v-if="show">你好，uni-app</view>
    </cmd-transition>
    <cmd-transition name="bounce">
      <view v-if="show">你好，uni-app</view>
    </cmd-transition>
    <cmd-transition name="punch">
      <view v-if="show">你好，uni-app</view>
    </cmd-transition>
    <cmd-transition name="zoom">
      <view v-if="show">你好，uni-app</view>
    </cmd-transition>
    <cmd-transition name="fly">
      <view v-if="show">你好，uni-app</view>
    </cmd-transition>
    <!-- #endif -->
    <button type="primary" v-on:click="show = !show">你好</button>
    <!-- #ifndef H5 -->
    <cmd-transition v-if="show" name="fade">
      <view>你好，uni-app</view>
    </cmd-transition>
    <cmd-transition v-if="show" name="fade-up">
      <view>你好，uni-app</view>
    </cmd-transition>
    <cmd-transition v-if="show" name="fade-down">
      <view>你好，uni-app</view>
    </cmd-transition>
    <cmd-transition v-if="show" name="fade-left">
      <view>你好，uni-app</view>
    </cmd-transition>
    <cmd-transition v-if="show" name="fade-right">
      <view>你好，uni-app</view>
    </cmd-transition>
    <cmd-transition v-if="show" name="slide-up">
      <view>你好，uni-app</view>
    </cmd-transition>
    <cmd-transition v-if="show" name="slide-down">
      <view>你好，uni-app</view>
    </cmd-transition>
    <cmd-transition v-if="show" name="slide-left">
      <view>你好，uni-app</view>
    </cmd-transition>
    <cmd-transition v-if="show" name="slide-right">
      <view>你好，uni-app</view>
    </cmd-transition>
    <cmd-transition v-if="show" name="bounce">
      <view>你好，uni-app</view>
    </cmd-transition>
    <cmd-transition v-if="show" name="punch">
      <view>你好，uni-app</view>
    </cmd-transition>
    <cmd-transition v-if="show" name="zoom">
      <view>你好，uni-app</view>
    </cmd-transition>
    <cmd-transition v-if="show" name="fly">
      <view>你好，uni-app</view>
    </cmd-transition>
    <!-- #endif -->
  </view>
</template>

<script>
  import cmdTransition from "@/components/cmd-transition/cmd-transition.vue"
  export default {
    components: {
      cmdTransition
    },
    data() {
      return {
        show: true
      };
    },
    methods: {}
  }
</script>

<style>

</style>

<template>
  <view>
    <view class="">
      幕帘curtain
    </view>
    <view>
      <!-- <cmd-curtain></cmd-curtain> -->
      <cmd-curtain :visible="visible" mode="top-right" @close="fnCurtainClose">
        <cmd-avatar :src="img"></cmd-avatar>
        <image mode="aspectFit" :src="img" @click="fnCurtainClick"></image>
      </cmd-curtain>
      <button type="primary" @tap="fnCurtain">幕帘</button>
    </view>
  </view>
</template>

<script>
  import logo from "@/static/logo.png"
  import cmdCurtain from "@/components/cmd-curtain/cmd-curtain.vue"
  import cmdAvatar from "@/components/cmd-avatar/cmd-avatar.vue"
  
  export default {
    components: {
      cmdCurtain,
      cmdAvatar
    },
    data() {
      return {
        visible: false,
        img: logo,
        // img: 'http://storage.360buyimg.com/mtd/home/32443566_635798770100444_2113947400891531264_n1533825816008.jpg'
      };
    },
    
    mounted() {
      setTimeout(()=>{
        this.visible = true
      },1000)
    },

    methods: {
      fnCurtain() {
        this.visible = !this.visible;
      },
      fnCurtainClick() {
        console.log('点击');
      },
      fnCurtainClose(){
        console.log('关闭幕帘');
      }
    }
  }
</script>

<style>

</style>

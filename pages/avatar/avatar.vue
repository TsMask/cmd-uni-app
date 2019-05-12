<template>
  <view>
    <view class="">
      头像avatar
    </view>
    <view>
      <view>默认头像</view>
      <cmd-avatar></cmd-avatar>
      <cmd-avatar :src='img'></cmd-avatar>
      <cmd-avatar icon='sketch'></cmd-avatar>
      <cmd-avatar text='C'></cmd-avatar>

      <view>圆形头像</view>
      <cmd-avatar size='sm' :src='img'></cmd-avatar>
      <cmd-avatar :src='img'></cmd-avatar>
      <cmd-avatar size='lg' :src='img'></cmd-avatar>
      <cmd-avatar :size='150' shape='circle' :src='img'></cmd-avatar>

      <view>圆角矩形头像</view>
      <cmd-avatar shape='square' size='sm' :src='img'></cmd-avatar>
      <cmd-avatar shape='square' :src='img'></cmd-avatar>
      <cmd-avatar shape='square' size='lg' :src='img'></cmd-avatar>
      <cmd-avatar :size='150' shape='square' :src='img'></cmd-avatar>

      <view>圆形头像（支持文本）</view>
      <cmd-avatar shape='circle' size='sm' text='C'></cmd-avatar>
      <cmd-avatar shape='circle' text='C'></cmd-avatar>
      <cmd-avatar shape='circle' size='lg' text='C'></cmd-avatar>
      <cmd-avatar :size='150' shape='circle' text='C'></cmd-avatar>
      <cmd-avatar :make="{'color': '#f56a00','background-color': '#fde3cf'}" :size='150' shape='circle' text='C'></cmd-avatar>

      <view>圆角矩形头像（支持文本）</view>
      <cmd-avatar shape='square' size='sm' text='C'></cmd-avatar>
      <cmd-avatar shape='square' text='C'></cmd-avatar>
      <cmd-avatar shape='square' size='lg' text='C'></cmd-avatar>
      <cmd-avatar :size='150' shape='square' text='C'></cmd-avatar>
      <cmd-avatar :make="{'color': '#f56a00','background-color': '#fde3cf'}" :size='150' shape='square' text='C'></cmd-avatar>

      <view>圆形头像（支持图标）</view>
      <cmd-avatar shape='circle' size='sm' icon='sketch'></cmd-avatar>
      <cmd-avatar shape='circle' icon='sketch'></cmd-avatar>
      <cmd-avatar shape='circle' size='lg' icon='sketch'></cmd-avatar>
      <cmd-avatar :size='150' shape='circle' icon='sketch'></cmd-avatar>
      <cmd-avatar :make="{'color': '#f56a00','background-color': '#fde3cf'}" :size='150' shape='circle' icon='sketch'></cmd-avatar>

      <view>圆角矩形头像（支持图标）</view>
      <cmd-avatar shape='square' size='sm' icon='sketch'></cmd-avatar>
      <cmd-avatar shape='square' icon='sketch'></cmd-avatar>
      <cmd-avatar shape='square' size='lg' icon='sketch'></cmd-avatar>
      <cmd-avatar :size='150' shape='square' icon='sketch'></cmd-avatar>
      <cmd-avatar :make="{'color': '#f56a00','background-color': '#fde3cf'}" :size='150' shape='square' icon='sketch'></cmd-avatar>
    </view>
  </view>
</template>

<script>
  import logo from "@/static/logo.png"
  import cmdAvatar from "@/components/cmd-avatar/cmd-avatar.vue"
  
  export default {
    components: {
      cmdAvatar
    },
    data() {
      return {
        img: logo,
        // img: 'http://storage.360buyimg.com/mtd/home/32443566_635798770100444_2113947400891531264_n1533825816008.jpg'
      };
    }
  }
</script>

<style>

</style>

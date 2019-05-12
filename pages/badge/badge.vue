<template>
  <view>
    <view class="">
      微标badge
    </view>
    <view>
      组件里使用 slot 嵌套的其他组件时不支持 v-for
      <br />

      <view class="uni-h2">
        cmd-badge组件
      </view>
      <cmd-badge value="9999sdfsdf"></cmd-badge>
      <br />
      <cmd-badge dot :make="{'background':'#898989'}">
        <cmd-avatar text="14"></cmd-avatar>
      </cmd-badge>
      <cmd-badge dot>
        <cmd-avatar shape="square" text="U"></cmd-avatar>
      </cmd-badge>
      <br />
      <cmd-badge value="9999sdfsdf">
        <cmd-avatar icon="add"></cmd-avatar>
      </cmd-badge>
      <br />
      <cmd-badge :value="9999">
        <cmd-avatar :src="img" @click="fnBadgeClick"></cmd-avatar>
      </cmd-badge>



      <br /><br /><br />


      <view class="uni-h2">
        uni-badge组件
      </view>
      <uni-badge text="点击事件" @click="fnBadgeClick"></uni-badge>
      <uni-badge text="3" type="primary" :inverted="true"></uni-badge>
      <uni-badge text="3" type="primary" :inverted="false"></uni-badge>
      <uni-badge text="3" type="primary" size="small"></uni-badge>
      <uni-badge text="3" type="primary" size="normal"></uni-badge>
    </view>
  </view>
</template>

<script>
  import logo from "@/static/logo.png"
  import cmdBadge from "@/components/cmd-badge/cmd-badge.vue"
  import cmdAvatar from "@/components/cmd-avatar/cmd-avatar.vue"
  import uniBadge from "@/components/uni-badge/uni-badge.vue"

  export default {
    components: {
      cmdBadge,
      cmdAvatar,
      uniBadge
    },
    data() {
      return {
        img: logo,
        // img: 'http://storage.360buyimg.com/mtd/home/32443566_635798770100444_2113947400891531264_n1533825816008.jpg'
      };
    },
    methods: {
      fnBadgeClick() {
        console.log('??');
      }
    }
  }
</script>

<style>

</style>

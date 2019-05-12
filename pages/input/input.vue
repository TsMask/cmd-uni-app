<template>
  <view>
    <cmd-input type="digit" placeholder="digit"></cmd-input>
    <cmd-input type="idcard" placeholder="idcard"></cmd-input>
    <cmd-input type="number" placeholder="number"></cmd-input>
    <cmd-input type="text" placeholder="text"></cmd-input>

    <cmd-input placeholder="最大输入长度12" maxlength="12"></cmd-input>
    <cmd-input placeholder="禁用输入" disabled></cmd-input>
    <cmd-input placeholder="自动获取焦点" focus></cmd-input>
    <cmd-input value="初始文本" type="text" placeholder="text文本清除按钮" clearable></cmd-input>
    <cmd-input type="password" placeholder="password密码可见" displayable></cmd-input>

    <cmd-input v-model="tx" placeholder="修改占位符样式" :placeholder-style="{'color':'#f44336'}" @focus="fnFocus" @blur="fnBlur" @input="fnInput"
      @confirm="fnConfirm"></cmd-input>

  </view>
</template>

<script>
  import cmdInput from '@/components/cmd-input/cmd-input.vue'
  import cmdAvatar from '@/components/cmd-avatar/cmd-avatar.vue'

  export default {
    components: {
      cmdInput,
      cmdAvatar
    },
    data() {
      return {
        tx: ''
      };
    },
    methods: {
      fnFocus(e) {
        console.log(this.tx);
        console.log('focus - ', e);
      },
      fnBlur(e) {
        console.log('blur - ', e);
      },
      fnInput(e) {
        console.log('input - ', e);
      },
      fnConfirm(e) {
        console.log('confirm - ', e);
      }
    }
  }
</script>

<style>

</style>

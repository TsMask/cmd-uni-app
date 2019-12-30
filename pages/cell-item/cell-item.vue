<template>
  <view>
    <view class="">
      列表单元 cmd-cell-item
    </view>
 
    <cmd-cell-item addon="附加文案" arrow></cmd-cell-item>
    <cmd-cell-item title="普通条目" />
    <cmd-cell-item title="动作条目" arrow @click="fnClick" />

    <cmd-cell-item title="交通银行(尾号3089)" brief="展示摘要描述" addon="附加文案" arrow />
    <cmd-cell-item title="交通银行(尾号3089)" brief="展示摘要描述" disabled addon="禁用项" />
    <cmd-cell-item title="交通银行(尾号3089)" brief="展示摘要描述" show-switch @switch="fnClick" switch-color="#2f86f6" />

    <cmd-cell-item title="普通条目" addon="附加文案" addon2="面向金融场景的Vue移动端UI组件库，丰富、灵活、实用，快速搭建优质的金融类产品，让复杂的金融场景变简单。基于「合理、好用」设计价值观，从交互操作、视觉抽象、图形可视等角度共同解决问题。" />

    <cmd-cell-item title="插槽" slot-left addon="附加文案">
      <cmd-avatar icon='user' :size="50" :make="{'color':'#2f86f6','background':'#111a34'}"></cmd-avatar>
    </cmd-cell-item>

  </view>
</template>

<script>
  import cmdCellItem from '@/components/cmd-cell-item/cmd-cell-item.vue'
  import cmdAvatar from '@/components/cmd-avatar/cmd-avatar.vue'

  export default {
    components: {
      cmdCellItem,
      cmdAvatar
    },
    data() {
      return {

      };
    },
    methods: {
      fnClick(e) {
        console.log(e);
      }
    }
  }
</script>

<style>

</style>

<template>
  <view>
    <view class="">
      列表单元cellitem
    </view>



    <view class="uni-h2">
      列表单元 uni-list
    </view>
    List 一般用法
    <uni-list>
      <uni-list-item title="标题文字" show-arrow="false"></uni-list-item>
      <uni-list-item title="标题文字"></uni-list-item>
      <uni-list-item title="标题文字" show-badge="true" badge-text="12"></uni-list-item>
      <uni-list-item title="禁用状态" disabled="true" show-badge="true" badge-text="12"></uni-list-item>
      <uni-list-item title="标题文字" show-extra-icon="true" :extra-icon="{color: '#4cd964',size: '22',type: 'spinner'}">
      </uni-list-item>
      <uni-list-item title="标题文字" thumb="http://img-cdn-qiniu.dcloud.net.cn/new-page/hx.png"></uni-list-item>
      <uni-list-item title="标题文字" show-switch="true" show-arrow="false"></uni-list-item>
    </uni-list>





    <view class="uni-h2">
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
  import uniList from '@/components/uni-list/uni-list.vue'
  import uniListItem from '@/components/uni-list/uni-list-item.vue'
  import cmdCellItem from '@/components/cmd-cell-item/cmd-cell-item.vue'
  import cmdAvatar from '@/components/cmd-avatar/cmd-avatar.vue'

  export default {
    components: {
      uniList,
      uniListItem,
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

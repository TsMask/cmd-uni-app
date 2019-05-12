<template>
  <view>
    <button class="btn" @click="fnOpen('avatar')">头像</button>
    <button class="btn" @click="fnOpen('badge')">微标</button>
    <button class="btn" @click="fnOpen('cell-item')">列表单元项</button>
    <button class="btn" @click="fnOpen('curtain')">幕帘</button>
    <button class="btn" @click="fnOpen('divider')">分隔线</button>
    <button class="btn" @click="fnOpen('notice-bar')">通知栏</button>
    <button class="btn" @click="fnOpen('icon')">图标</button>
    <button class="btn" @click="fnOpen('input')">输入框</button>
    <button class="btn" @click="fnOpen('progress')">进度条</button>
    <button class="btn" @click="fnOpen('result-page')">结果页</button>
    <button class="btn" @click="fnOpen('nav-bar')">顶部导航栏</button>
    <button class="btn" @click="fnOpen('bottom-nav')">底部导航栏</button>
    <button class="btn" @click="fnOpen('tool-bar')">顶部工具栏</button>
    <button class="btn" @click="fnOpen('page-body')">自定义顶/底部导航-填充内容区</button>
    <button class="btn" @click="fnOpen('transition')">动画</button>
    <button class="btn" @click="fnOpen('html-parser')">HTML 文本解析器</button>
  </view>
</template>

<script>
  export default {
    data() {
      return {}
    },
    methods: {
      fnOpen(page) {
        uni.navigateTo({
          url: `/pages/${page}/${page}`
        });
      }
    }
  }
</script>

<style>
  .btn {
    background: #f44336;
    color: #fff;
    margin: 20upx 0;
  }
</style>

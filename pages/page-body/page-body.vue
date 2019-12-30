<template>
  <view>
    <!-- 顶部导航栏组件 -->
    <cmd-nav-bar back :title="title" iconTwo="add"></cmd-nav-bar>
    <!-- 内容区 start -->
    <cmd-page-body type="top-bottom" background-color="#f5f5f5">
      <view v-if="current == 0">
        首页
      </view>
      <view v-if="current == 1">
        分享
      </view>
      <view v-if="current == 2">
        刷新
      </view>
      <view v-if="current == 3">
        菜单
      </view>
    </cmd-page-body>
    <!-- 内容区 end -->
    <!-- 底部导航栏组件 -->
    <cmd-bottom-nav background-color="#ffffff" font-color="#f9a0b9" active-font-color="#ff061d" @click="getBottomNavCurrent"
      :current="current" :list="list"></cmd-bottom-nav>
  </view>
</template>

<script>
  import cmdNavBar from "@/components/cmd-nav-bar/cmd-nav-bar.vue"
  import cmdBottomNav from "@/components/cmd-bottom-nav/cmd-bottom-nav.vue"
  import cmdPageBody from "@/components/cmd-page-body/cmd-page-body.vue"

  export default {
    components: {
      cmdBottomNav,
      cmdNavBar,
      cmdPageBody
    },

    data() {
      return {
        bodyHeight: 0,
        title: '首页',
        current: 0,
        list: [{
            "pagePath": "/pages/bottom-nav/home/home",
            "text": "首页",
            "icon": "home"
          },
          {
            "pagePath": "/pages/bottom-nav/lottery/lottery",
            "text": "分享",
            "icon": "share",
            "srcSelect": "../../static/bottom-nav/lotteryHL.png"
          },
          {
            "pagePath": "/pages/bottom-nav/find/find",
            "text": "刷新",
            "icon": "reload"
          },
          {
            "pagePath": "/pages/bottom-nav/person/person",
            "text": "菜单",
            "icon": "menu"
          }
        ]
      };
    },

    methods: {
      /**
       * 获取导航栏选项
       */
      getBottomNavCurrent(e) {
        this.current = e.select;
        this.title = e.item.text;
        console.log(e);
      }
    }
  }
</script>

<style>
</style>

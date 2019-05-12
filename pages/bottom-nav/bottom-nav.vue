<template>
  <view>
    <!-- <cmd-bottom-nav></cmd-bottom-nav> -->
    <cmd-bottom-nav background-color="linear-gradient(to right, rgb(17, 153, 142), rgb(56, 239, 125))" @click="bottomNav"
      :current="current" :list="list" text-auto></cmd-bottom-nav>
    <view class="cmd-page-body">
      <view v-for="i in 99" :key="i">
        bottom - {{i}}
      </view>
    </view>
  </view>
</template>

<script>
  import cmdBottomNav from "@/components/cmd-bottom-nav/cmd-bottom-nav.vue"
  export default {
    components: {
      cmdBottomNav
    },
    data() {
      return {
        current: 0,
        list: [{
            "pagePath": "/pages/tabbar/home/home",
            "text": "首页",
            "icon": "home"
            // src 大小限制为40kb，建议尺寸为 81px * 81px
            // "src": "../../static/iocn-tabbar/home.png",
            // "srcSelect": "../../static/iocn-tabbar/homeHL.png"
          },
          {
            "pagePath": "/pages/tabbar/lottery/lottery",
            "text": "邮件",
            "icon": "mail",
            // src 大小限制为40kb，建议尺寸为 81px * 81px
            // "src": "../../static/iocn-tabbar/home.png",
            // "srcSelect": "../../static/iocn-tabbar/homeHL.png"
          },
          {
            "pagePath": "/pages/tabbar/my/my",
            "text": "信息",
            "icon": "message"
            // src 大小限制为40kb，建议尺寸为 81px * 81px
            // "src": "../../static/iocn-tabbar/home.png",
            // "srcSelect": "../../static/iocn-tabbar/homeHL.png"
          }
        ]
      };
    },
    methods: {
      bottomNav(e) {
        this.current = e.select;
        uni.setNavigationBarTitle({
          title: e.item.text
        })
      }
    }
  }
</script>

<style>
  .cmd-page-body {
    margin-bottom: 118upx;
  }
</style>

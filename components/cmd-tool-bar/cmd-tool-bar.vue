<template>
  <view :class="fixed ? 'cmd-tool-bar-fixed' : ''" :style="setBackgroundColor">
    <view class="status-bar"></view>
    <view class="cmd-tool-bar">
      <view v-if="back || iconOne" @tap="$_iconOneClick" class="cmd-tool-bar-icon">
        <cmd-icon :type="back ?'chevron-left' : iconOne" size="24" :color="setFontColor"></cmd-icon>
      </view>
      <view class="cmd-tool-bar-title" :style="'color:'+setFontColor">{{title}}</view>
      <view class="cmd-tool-bar-spacer"></view>
      <view v-if="iconThree && iconFour" @tap="$_iconFourClick" class="cmd-tool-bar-icon">
        <cmd-icon :type="iconFour" size="24" :color="setFontColor"></cmd-icon>
      </view>
      <view v-if="iconTwo && iconThree" @tap="$_iconThreeClick" class="cmd-tool-bar-icon">
        <cmd-icon :type="iconThree" size="24" :color="setFontColor"></cmd-icon>
      </view>
      <view v-if="iconTwo" @tap="$_iconTwoClick" class="cmd-tool-bar-icon">
        <cmd-icon :type="iconTwo" size="24" :color="setFontColor"></cmd-icon>
      </view>
    </view>
  </view>
</template>

<script>
  import cmdIcon from "../cmd-icon/cmd-icon.vue"

  /**  
   * 工具栏组件 
   * @description 工具栏是安卓md风格的，标题加图标。  
   * @tutorial http://ext.dcloud.net.cn/plugin?id=189  
   * @property {Boolean} fixed 工具栏固定到页面顶部 - 默认true  
   * @property {Boolean} back 工具栏左侧返回按钮 - 默认false,点击返回上层  
   * @property {String} title 工具栏左侧标题  
   * @property {String} font-color 工具栏内文字、图标的颜色  
   * @property {String} background-color 工具栏背景颜色  
   * @property {String} icon-one 工具栏图标一  
   * @property {String} icon-two 工具栏图标二  
   * @property {String} icon-three 工具栏图标三  
   * @property {String} icon-four 工具栏图标四  
   * @event {Function} iconOne 工具栏图标一 点击事件  
   * @event {Function} iconTwo 工具栏图标二 点击事件  
   * @event {Function} iconThree 工具栏图标三 点击事件  
   * @event {Function} iconFour 工具栏图标四 点击事件  
   * @example <cmd-tool-bar title="标题"></cmd-tool-bar>  
   */
  export default {
    name: 'cmd-tool-bar',

    components: {
      cmdIcon
    },

    props: {
      /**
       * 固定到页面顶部
       */
      fixed: {
        type: Boolean,
        default: true
      },
      /**
       * 文字图标颜色
       */
      fontColor: {
        type: String,
        default: ''
      },
      /**
       * 工具栏背景颜色
       */
      backgroundColor: {
        type: String,
        default: ''
      },
      /**
       * 工具栏标题
       */
      title: {
        type: String,
        default: 'Title'
      },
      /**
       * 工具栏返回按钮，默认点击返回上层
       */
      back: {
        type: Boolean,
        default: false
      },
      /**
       * 图标一不可与返回按钮同显
       */
      iconOne: {
        type: String,
        default: ''
      },
      /**
       * 图标二
       */
      iconTwo: {
        type: String,
        default: ''
      },
      /**
       * 图标三，须显有图标二
       */
      iconThree: {
        type: String,
        default: ''
      },
      /**
       * 图标四
       */
      iconFour: {
        type: String,
        default: ''
      }
    },

    computed: {
      /**
       * 设置标题图标颜色
       */
      setFontColor() {
        let fontColor = '#fff';
        if (this.fontColor != '') {
          fontColor = this.fontColor;
        }
        return fontColor;
      },
      /**
       * 设置背景颜色
       */
      setBackgroundColor() {
        let backgroundColor = '#3f51b5';
        if (this.backgroundColor) {
          backgroundColor = `background: ${this.backgroundColor};`;
        }
        return backgroundColor;
      }
    },

    methods: {
      /**
       * 图标一点击事件
       */
      $_iconOneClick() {
        if (this.back) {
          uni.navigateBack()
        } else {
          this.$emit("iconOne");
        }
      },
      /**
       * 图标二点击事件
       */
      $_iconTwoClick() {
        this.$emit("iconTwo");
      },
      /**
       * 图标三点击事件
       */
      $_iconThreeClick() {
        this.$emit("iconThree");
      },
      /**
       * 图标四点击事件
       */
      $_iconFourClick() {
        this.$emit("iconFour");
      }
    }

  }
</script>

<style>
  /* 固定到页面顶部 */
  .cmd-tool-bar-fixed {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 1000;
    background: #3f51b5;
  }

  /*沉浸状态栏变化*/
  .status-bar {
    box-sizing: border-box;
    display: block;
    width: 100%;
    margin-bottom: -3upx;
    height: var(--status-bar-height);
    line-height: var(--status-bar-height);
    background: transparent;
  }

  /*工具栏默认*/
  .cmd-tool-bar {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    width: 100%;
    height: 118upx;
    line-height: 118upx;
    color: #fff;
    background: transparent;
    box-shadow: 0 6upx 6upx -3upx rgba(0, 0, 0, 0.15);
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }

  .cmd-tool-bar-title {
    margin: 0 34upx;
    font-size: 42upx;
    font-weight: 500;
    letter-spacing: 2upx;
  }

  .cmd-tool-bar-spacer {
    margin: 0;
    flex-grow: 1;
  }

  .cmd-tool-bar-icon {
    width: 100upx;
    min-width: 100upx;
    height: 100upx;
    line-height: 100upx;
    text-align: center;
    margin: 0 10upx;
  }
</style>

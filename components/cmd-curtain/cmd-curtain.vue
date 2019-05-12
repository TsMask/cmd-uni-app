<template>
  <view :class="[isOpen ? 'cmd-curtain' : 'cmd-curtain-closed']">
    <view class="cmd-curtain-container">
      <view class="cmd-curtain-body">
        <slot></slot>
        <view class="cmd-curtain-btn-close" :class="setModeClass" @tap="$_close"></view>
      </view>
    </view>
  </view>
</template>

<script>
  /**  
   * 幕帘组件  
   * @description 可以用来放置广告提示内容  
   * @tutorial http://ext.dcloud.net.cn/plugin?id=179  
   * @property {Boolean} visible - 显示幕帘层，默认false   
   * @property {String} mode 按钮方向模式 - top、top-right、top-left bottom、bottom-right、bottom-left  
   * @event {Function} close 幕帘打开后的关闭按钮 关闭事件  
   * @example cmd-curtain :visible="true" mode="top-right">view</cmd-curtain> 
   */
  export default {
    name: 'cmd-curtain',

    props: {
      /**
       * 显示状态
       */
      visible: {
        type: Boolean,
        default: false
      },
      /**
       * 按钮方向模式
       */
      mode: {
        type: String,
        default: 'bottom'
      }
    },

    data() {
      return {
        // 幕帘显示
        isOpen: false
      }
    },

    computed: {
      // 按钮方向样式
      setModeClass() {
        let modeClass = "cmd-curtain-btn-close-"
        if (this.mode != 'bottom') {
          modeClass += this.mode;
        } else {
          modeClass += this.mode;
        }
        return modeClass
      }
    },

    watch: {
      /**
       * 监听显示状态
       */
      visible(val) {
        this.isOpen = true;
      }
    },

    methods: {
      /**
       * 关闭事件
       */
      $_close(e) {
        this.isOpen = false;
        setTimeout(() => {
          this.$emit('close', e)
        }, 300)
      }
    }

  }
</script>

<style>
  .cmd-curtain {
    display: block;
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: rgba(0, 0, 0, 0.3);
    z-index: 1080;
  }

  .cmd-curtain-container {
    display: flex;
    position: relative;
    margin: 0 auto;
    width: 80%;
    height: 100%;
    justify-content: center;
    align-items: center;
    box-sizing: border-box;
    opacity: 1;
  }

  .cmd-curtain-body {
    position: relative;
    width: 100%;
  }

  .cmd-curtain-btn-close {
    display: flex;
    position: absolute;
    width: 64upx;
    height: 64upx;
    margin-left: -32upx;
    left: 50%;
    bottom: -88upx;
    align-items: center;
    justify-content: center;
    border: 2upx solid #FFF;
    border-radius: 50%;
    box-sizing: border-box;
    z-index: 1080;
  }

  .cmd-curtain-btn-close::before,
  .cmd-curtain-btn-close::after {
    content: "";
    position: absolute;
    top: 50%;
    left: 50%;
    display: inline-block;
    width: 34upx;
    height: 2upx;
    border-radius: 1upx;
    background: #FFF;
  }

  .cmd-curtain-btn-close::before {
    transform: translate3d(-50%, -50%, 0) rotate(45deg);
  }

  .cmd-curtain-btn-close::after {
    transform: translate3d(-50%, -50%, 0) rotate(-45deg);
  }

  /* 关闭按钮方向位置 */
  .cmd-curtain-btn-close-top {
    margin-left: -32upx;
    top: -88upx;
    left: 50%;
    bottom: auto;
  }

  .cmd-curtain-btn-close-top-left {
    top: -88upx;
    left: 0;
    bottom: auto;
  }

  .cmd-curtain-btn-close-top-right {
    top: -88upx;
    left: auto;
    right: 0;
    bottom: auto;
  }

  .cmd-curtain-btn-close-bottom {
    margin-left: -32upx;
    bottom: -88upx;
    left: 50%;
  }

  .cmd-curtain-btn-close-bottom-left {
    bottom: -88upx;
    left: 0;
  }

  .cmd-curtain-btn-close-bottom-right {
    bottom: -88upx;
    left: auto;
    right: 0;
  }

  /* 关闭 */
  .cmd-curtain-closed {
    visibility: hidden;
    display: none;
  }
</style>

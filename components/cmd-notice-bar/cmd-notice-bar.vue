<template>
  <view v-if="isShow" class="cmd-notice-bar" :class="[round ? 'cmd-notice-bar-round':'',type]" :style="setNoticeStyle">
    <view class="cmd-notice-bar-left" v-if="icon">
      <cmd-icon :type="icon" size="16" :color="setIconColor"></cmd-icon>
    </view>
    <view class="cmd-notice-bar-content" :class="[rows && !scrollable ? 'cmd-notice-bar-multi-content':'']">
      <view @tap="$_click" v-text="text" :style="setSingleEllStyle" :class="[scrollable ? 'cmd-notice-bar-content-animate':'']"></view>
    </view>
    <view class="cmd-notice-bar-right" v-if="mode">
      <cmd-icon :type="setModeIcon" size="16" :color="setIconColor" @click="$_mode"></cmd-icon>
    </view>
  </view>
</template>

<script>
  import cmdIcon from '../cmd-icon/cmd-icon.vue'

  /**  
   * 通知栏组件  
   * @description 通常用于系统提醒、活动提醒等通知  
   * @tutorial http://ext.dcloud.net.cn/plugin?id=178  
   * @property {String} text 显示文字  
   * @property {String} mode 右侧提示类型模式 - close关闭x图案、link连接详情>图案  
   * @property {String} type 情景类型 - default默认蓝色、activity活动黄色、warning警告红色  
   * @property {Number} time 显示时长 - 单位为ms，默认不消失为0  
   * @property {Boolean} round 圆角显示 - 默认false  
   * @property {Boolean} rows 多行文本显示 - 默认false  
   * @property {Boolean} scrollable 是否滚动 - 为true时，为单行滚动，默认false  
   * @property {String} icon 左侧状态图标 - icon图标类型，列如：home  
   * @property {Object} make 通知栏自定义样式 - 一般颜色大小字体{}  
   * @event {Function} click 通知文本 点击事件  
   * @event {Function} close 关闭x 点击事件  
   * @event {Function} link 更多> 点击事件  
   * @example <cmd-notice-bar text="通知信息显示"></cmd-notice-bar>  
   */
  export default {
    name: 'cmd-notice-bar',

    components: {
      cmdIcon
    },

    props: {
      /**
       * 显示文本
       */
      text: {
        tyep: String,
        default: ''
      },
      /**
       * 右侧提示类型 close/link
       */
      mode: {
        type: String,
        default: ''
      },
      /**
       * 情景类型 default/activity/warning
       */
      type: {
        type: String,
        default: 'default'
      },
      /**
       * 显示时长 单位为ms，不需要自动消失可将其置为0
       */
      time: {
        type: Number,
        default: 0,
      },
      /**
       * 圆角显示
       */
      round: {
        type: Boolean,
        default: false,
      },
      /**
       * 多行文本显示
       */
      rows: {
        type: Boolean,
        default: false,
      },
      /**
       * 滚动文本
       */
      scrollable: {
        type: Boolean,
        default: false,
      },
      /**
       * 左侧状态图标
       */
      icon: {
        type: String,
        default: '',
      },
      /**
       * 通知栏自定义样式
       */
      make: {
        type: Object,
        default: () => {
          return {
            'background-color': '',
            'color': ''
          }
        }
      }
    },

    data() {
      return {
        /**
         * 通知栏显示
         */
        isShow: true
      }
    },

    computed: {
      /**
       * 右侧提示图标
       */
      setModeIcon() {
        if (this.mode === 'link') {
          return 'chevron-right';
        } else if (this.mode === 'close') {
          return 'close';
        }
      },
      /**
       * 左侧提示图标
       */
      setIconColor() {
        let iconColor = '';
        if (this.type === 'activity') {
          iconColor = '#FF843D';
        } else if (this.type === 'warning') {
          iconColor = '#FF5B60';
        } else {
          iconColor = '#2F86F6';
        }
        return iconColor;
      },
      /**
       * 自定义style
       */
      setNoticeStyle() {
        let noticeStyle = '';
        for (let it in this.make) {
          noticeStyle += `${it}:${this.make[it]};`;
        }
        return noticeStyle;
      },
      /**
       * 单行文本溢出省略
       */
      setSingleEllStyle() {
        if (!this.rows && !this.scrollable) {
          return 'text-overflow: ellipsis;white-space:nowrap;overflow:hidden;';
        }
        return '';
      }
    },

    mounted() {
      if (this.time) {
        this.$_hide(this.time)
      }
    },

    methods: {
      /**
       * 定时关闭通知栏
       */
      $_hide(time) {
        setTimeout(() => {
          this.isShow = false
        }, time)
      },
      /**
       * 右侧图标点击事件
       */
      $_mode(e) {
        if (this.mode === 'close') {
          this.isShow = false;
          this.$emit('close', e)
        }
        if (this.mode === 'link') {
          this.$emit('link', e)
        }
      },
      /**
       * 通知栏文字点击
       */
      $_click(e) {
        this.$emit('click', e)
      }
    },
  }
</script>

<style>
  .cmd-notice-bar {
    display: flex;
    z-index: 1301;
    font-size: 26upx;
    min-height: 64upx;
    background-color: rgba(89, 158, 248, 0.08);
    color: #2F86F6;
    position: relative;
    padding-left: 32upx;
    box-sizing: border-box;
  }

  .cmd-notice-bar.cmd-notice-bar-round {
    border-radius: 32upx;
  }

  .cmd-notice-bar.activity {
    background-color: #FFEDDE;
    color: #FF843D;
  }

  .cmd-notice-bar.warning {
    background-color: #FFEEEF;
    color: #FF5B60;
  }

  .cmd-notice-bar-left,
  .cmd-notice-bar-right {
    display: flex;
    align-items: center;
  }

  .cmd-notice-bar-left {
    padding-right: 12upx;
  }

  .cmd-notice-bar-right {
    padding-right: 32upx;
  }

  .cmd-notice-bar-content {
    flex: 1;
    margin: auto;
    width: auto;
    line-height: 64upx;
    white-space: nowrap;
    overflow: hidden;
  }

  .cmd-notice-bar-content.cmd-notice-bar-multi-content {
    padding: 20upx 32upx 20upx 0;
    line-height: 36upx;
    white-space: normal;
  }

  .cmd-notice-bar-content .cmd-notice-bar-content-animate {
    padding-left: 100%;
    display: inline-block;
    animation: cmd-notice-bar-animation linear 16s infinite both;
  }

  @keyframes cmd-notice-bar-animation {
    0% {
      transform: translate3d(0, 0, 0);
    }

    100% {
      transform: translate3d(-100%, 0, 0);
    }
  }
</style>

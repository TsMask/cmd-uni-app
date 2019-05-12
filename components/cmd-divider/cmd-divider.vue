<template>
  <view class="cmd-divider" :style="setHeightStyle" @tap="$_click">
    <view v-if="!content" class="cmd-divider-content">
      <slot></slot>
    </view>
    <view class="cmd-divider-content" :style="setFontStyle" v-text="content"></view>
    <view class="cmd-divider-line" :style="setLineStyle"></view>
  </view>
</template>

<script>
  /**  
   * 分隔线组件  
   * @description 强调单独的内容区域和需要更明显的视觉分离的部分。  
   * @tutorial http://ext.dcloud.net.cn/search?q=cmd  
   * @property {String} content 分隔线中间内容 - 默认无  
   * @property {String, Number} height 分隔线高度 - 默认:60px  
   * @property {String} font-color 文字颜色 - 默认:#999  
   * @property {String} font-size 文字大小 - 默认:18px  
   * @property {String} lineColor 线颜色 - 默认:24  
   * @event {Function} click 分隔线点击事件  
   * @example <cmd-divider content="分隔内容"></cmd-divider>  
   */
  export default {
    name: 'cmd-divider',

    props: {
      /**
       * 内容
       */
      content: {
        type: String,
        default: ''
      },
      /**
       * 高度
       */
      height: {
        type: [String, Number],
        default: ''
      },
      /**
       * 文字颜色
       */
      fontColor: {
        type: String,
        default: ''
      },
      /**
       * 文字大小
       */
      fontSize: {
        type: String,
        default: ''
      },
      /**
       * 线颜色
       */
      lineColor: {
        type: String,
        default: ''
      }
    },

    computed: {
      /**
       * 分隔线高度样式
       */
      setHeightStyle() {
        let heightStyle = '';
        if (this.height) {
          heightStyle += `height:${this.height}px;`;
        }
        return heightStyle;
      },
      /**
       * 分隔线文字样式
       */
      setFontStyle() {
        let fontStyle = '';
        if (this.fontColor) {
          fontStyle += `color:${this.fontColor};`;
        }
        if (this.fontSize) {
          fontStyle += `font-size:${this.fontSize}px;`;
        }
        return fontStyle;
      },
      /**
       * 分隔线颜色样式
       */
      setLineStyle() {
        let lineStyle = '';
        if (this.lineColor) {
          lineStyle += `background-color:${this.lineColor};`;
        }
        return lineStyle;
      }
    },

    methods: {
      /**
       * 点击分隔线
       * @param {Object} e点击对象
       */
      $_click(e) {
        this.$emit('click', e)
      }
    }

  }
</script>

<style>
  .cmd-divider {
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    width: 100%;
    height: 120upx;
    font-size: 36upx;
    text-align: center;
  }

  .cmd-divider-content {
    display: inline-block;
    position: relative;
    padding: 0 24upx;
    color: #999;
    font-size: 36upx;
    background: #FFF;
    z-index: 101;
  }

  .cmd-divider-line {
    position: absolute;
    top: 50%;
    left: 0;
    width: 100%;
    height: 3upx;
    background-color: #CCC;
    z-index: 100;
  }
</style>

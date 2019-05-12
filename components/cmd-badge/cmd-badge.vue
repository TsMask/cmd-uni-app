<template>
  <view class="cmd-badge" @tap="$_click">
    <slot></slot>
    <view :class="[dot? 'cmd-badge-dot':'cmd-badge-num']" :style="setBadgeStyle" v-text="setVal"></view>
  </view>
</template>

<script>
  /**  
   * 微标组件  
   * @description 主要用于突出显示新的或未读的项。  
   * @tutorial http://ext.dcloud.net.cn/search?q=cmd  
   * @property {Boolean} dot - 显示红色小圆点，默认false  
   * @property {String,Number} value - 显示字符数值，当长度大于5时后尾有省略号  
   * @property {Number} max-value - 数值最大值，对Number当数字超过时最大值+，默认99+  
   * @property {Object} make 自定义微标样式 - 颜色、背景、边距等  
   * @event {Function} click 整个微标组件 点击事件  
   * @example <cmd-badge value="33" >CMD</cmd-badge>  
   */
  export default {
    name: 'cmd-badge',

    props: {
      /**
       * 小红点
       */
      dot: {
        type: Boolean,
        default: false
      },
      /**
       * 字符数值
       */
      value: {
        type: [String, Number],
        default: ''
      },
      /**
       * 最大数值
       */
      maxValue: {
        type: Number,
        default: 99
      },
      /**
       * 自定义样式
       */
      make: {
        type: Object,
        default: () => {
          return {
            'color': ''
          }
        }
      }

    },

    computed: {
      // 微标样式
      setBadgeStyle() {
        let styleString = '';
        for (let it in this.make) {
          styleString += `${it}:${this.make[it]};`;
        }
        return styleString;
      },
      // 值处理
      setVal() {
        if (this.value === '' || this.value === null) {
          return '';
        } else if (typeof this.value === 'number') {
          return this.value > this.maxValue ? `${this.maxValue}+` : this.value;
        } else {
          return this.value.length > 5 ? `${this.value.substr(0,5)}...` : this.value;
        }
      }
    },

    methods: {
      // 点击事件
      $_click(e) {
        this.$emit('click', e)
      }
    }
  }
</script>

<style>
  .cmd-badge {
    position: relative;
    display: inline-block;
    font-size: 0;
    vertical-align: middle;
    /* 公共属性 */
  }

  .cmd-badge-dot {
    position: absolute;
    right: -8upx;
    top: -8upx;
    width: 24upx;
    height: 24upx;
    border-radius: 50%;
    overflow: hidden;
    background: #FF4949;
    box-shadow: 0 4upx 8upx 0 rgba(255, 73, 73, 0.2);
  }

  .cmd-badge-num {
    position: absolute;
    padding: 0 12upx;
    top: -16.8upx;
    right: -12upx;
    color: #FFF;
    font-size: 24upx;
    line-height: 1.4;
    border-radius: 16.8upx 16.8upx 16.8upx 0;
    background: #FF4949;
    box-shadow: 0 4upx 8upx 0 rgba(255, 73, 73, 0.2);
    transform: translate(50%, 0);
    overflow: hidden;
    z-index: 1;
  }
</style>

<template>
  <button
    class="hy-button"
    :class="[
      `hy-button-${type}`,
      {
        'is-plain': plain,
        'is-round': round,
        'is-circle': circle,
        'is-disabled': disabled
      }
    ]"
    :disabled="disabled"
    @click="sonClick"
  >
    <i v-if="icon" :class="icon"></i>
    <!-- 如果没有传入任何的内容 当我们没有传入插槽的时候 -->
    <span v-if="$slots.default">
      <slot></slot>
    </span>
  </button>
</template>

<script>
export default {
  name: 'HyButton',
  props: {
    type: {
      type: String,
      default: 'default'
    },
    plain: {
      type: Boolean,
      default: false
    },
    round: {
      type: Boolean,
      default: false
    },
    circle: {
      type: Boolean,
      default: false
    },
    disabled: {
      type: Boolean,
      default: false
    },
    icon: {
      type: String,
      default: ''
    }
  },
  methods: {
    sonClick (e) {
      this.$emit('click', e)
    }
  },
  created () {
    // console.log(this.plain)
    // console.log(this.$slots)
  }
}
</script>

<style lang='scss' scoped>
.hy-button {
  display: inline-block;
  line-height: 1;
  white-space: nowrap;
  cursor: pointer;
  background: #fff;
  border: 1px solid #dcdfe6;
  color: #606266;
  -webkit-appearance: none;
  text-align: center;
  box-sizing: border-box;
  outline: none;
  margin: 0;
  transition: 0.1s;
  font-weight: 500;
  /* 禁止元素的文字被选中 */
  -moz-user-select: none;
  -webkit-user-select: none;
  -ms-user-select: none;
  user-select: none;
  padding: 12px 20px;
  font-size: 14px;
  border-radius: 4px;
  &:hover,
  &:focus {
    color: #409eff;
    border-color: #c6e3ff;
    background-color: #ecf5ff;
  }
}
.hy-button-primary {
  color: #fff;
  background-color: #409dff;
  border-color: #409dff;
  &:hover,
  &:focus {
    color: #fff;
    border-color: #61b0ff;
    background-color: #61b0ff;
  }
}
.hy-button-success {
  color: #fff;
  background-color: #6baf24;
  border-color: #6baf24;
  &:hover,
  &:focus {
    color: #fff;
    border-color: #8cb85f;
    background-color: #8cb85f;
  }
}
.hy-button-warning {
  color: #fff;
  background-color: #e6a23c;
  border-color: #e6a23c;
  &:hover,
  &:focus {
    color: #fff;
    border-color: #ebb563;
    background-color: #ebb563;
  }
}
.hy-button-primary.is-plain {
  color: #a3a7ad;
  background-color: #ecf4ff;
  border-color: #aed8ff;
  &:hover,
  &:focus {
    color: #fff;
    border-color: #399bff;
    background-color: #399bff;
  }
}
.hy-button-success.is-plain {
  color: #61b137;
  background-color: #f0f0eb;
  border-color: #c2e0ae;
  &:hover,
  &:focus {
    color: #fff;
    border-color: #61b137;
    background-color: #61b137;
  }
}
//椭圆
.hy-button.is-round {
  border-radius: 20px;
  padding: 12px 23px;
}
//圆形按钮
.hy-button.is-circle {
  border-radius: 50%;
  padding: 12px;
}
//按钮后的文本
.hy-button [class*='hy-icon-'] + span {
  margin-left: 5px;
}
// 禁用
.hy-button.is-disabled,
.hy-button.is-disabled:focus,
.hy-button.is-disabled:hover {
    color: #c0c4cc;
    cursor: not-allowed;
    background-image: none;
    background-color: #fff;
    border-color: #ebeef5;
}
.hy-button-primary.is-disabled,
.hy-button-primary.is-disabled:active,
.hy-button-primary.is-disabled:focus,
.hy-button-primary.is-disabled:hover {
    color: #fff;
    background-color: #a0cfff;
    border-color: #a0cfff;
}
.hy-button-success.is-disabled,
.hy-button-success.is-disabled:active,
.hy-button-success.is-disabled:focus,
.hy-button-success.is-disabled:hover {
    color: #fff;
    background-color: #b3e19d;
    border-color: #b3e19d;
}
</style>

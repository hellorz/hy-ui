<template>
  <div class="hy-radio-group">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'HyRadioGroup',
  provide () {
    return {
      RadioGroup: this
    }
  },
  props: {
    value: null
  }
}
</script>

<style lang='scss' scoped>
</style>

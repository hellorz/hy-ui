<template>
  <div class="hy-checkbox-group">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'HyCheckboxGroup',
  props: {
    value: {
      type: Array,
      default: function () {
        return []
      }
    }
  },
  provide () {
    return {
      CheckboxGroup: this
    }
  }
}
</script>

<style>
</style>

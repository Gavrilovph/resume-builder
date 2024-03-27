<template>
  <button
  class="btn primary" :type="btnType"
  @click="$emit('load')"
  ><slot></slot></button>
</template>

<script>
export default {
  props: ['btnType'],
  emits: [
    'load'
  ]
}
</script>

<style lang="scss" scoped>

</style>

<template>
  <div class="avatar">
    <img :src="imgLink">
  </div>
</template>

<script>
export default {
  data () {
    return {
    }
  },
  props: [
    'imgLink'
  ]
}
</script>

<style lang="scss" scoped>

</style>

<template>
    <div class="card card-w70">
      <app-content-title></app-content-title>
      <app-avatar></app-avatar>
      <app-subtitle></app-subtitle>
      <app-text></app-text>
      <app-alert></app-alert>
    </div>
</template>

<script>
import AppContentTitle from './AppContentTitle.vue'
import AppAvatar from './AppAvatar.vue'
import AppSubtitle from './AppSubtitle.vue'
import AppText from './AppText.vue'
import AppAlert from './AppAlert.vue'

export default {
  components: {
    'app-content-title': AppContentTitle,
    'app-avatar': AppAvatar,
    'app-subtitle': AppSubtitle,
    'app-text': AppText,
    'app-alert': AppAlert
  }

}
</script>

<style lang="scss" scoped>

</style>

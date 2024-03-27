<template>
    <div class="card card-w70">
      <div v-if="rightStorage[0]">
        <div v-for="item in rightStorage" :key="item.block">
          <app-content-title v-if="item.block === 'title'">{{ item.text }}</app-content-title>
          <app-subtitle v-if="item.block === 'subtitle'">{{ item.text }}</app-subtitle>
          <app-text v-if="item.block === 'text'">{{ item.text }}</app-text>
          <app-avatar v-if="item.block === 'avatar'" :imgLink="item.text"></app-avatar>
        </div>
      </div>
      <app-alert v-else></app-alert>
    </div>
</template>

<script>
import AppContentTitle from './AppContentTitle.vue'
import AppAvatar from './AppAvatar.vue'
import AppSubtitle from './AppSubtitle.vue'
import AppText from './AppText.vue'
import AppAlert from './AppAlert.vue'

export default {
  props: ['rightStorage'],
  data () {
    return {
    }
  },
  components: {
    'app-content-title': AppContentTitle,
    'app-avatar': AppAvatar,
    'app-subtitle': AppSubtitle,
    'app-text': AppText,
    'app-alert': AppAlert
  },
  methods: {
    check () {
      console.log(this.titles)
    }
  },
  computed: {
  }

}
</script>

<style lang="scss" scoped>

</style>

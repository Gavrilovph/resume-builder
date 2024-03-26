<template>
  <div class="container column">
    <app-left-card @submit-handler="submitHandler"></app-left-card>
    <app-right-card></app-right-card>
  </div>
  <div class="container">
    <p>
      <app-button>Загрузить комментарии</app-button>
    </p>
    <app-comments
    v-if="comments === true"
    ></app-comments>
    <app-loader
    v-if="loader === true"
    ></app-loader>
  </div>
</template>

<script>
import AppLeftCard from './AppLeftCard'
import AppRightCard from './AppRightCard'
import AppLoader from './AppLoader'
import AppComments from './AppComments'
import AppButton from './AppButton'

export default {
  data () {
    return {
      loader: false,
      comments: false
      // blockStorage: [],
      // inputValue: '',
      // blockType: 'title'
    }
  },
  components: {
    'app-left-card': AppLeftCard,
    'app-right-card': AppRightCard,
    'app-loader': AppLoader,
    'app-comments': AppComments,
    'app-button': AppButton
  },
  methods: {
    // submitHandler () {
    //   this.blockStorage.push({ type: this.blockType, value: this.inputValue })
    //   console.log(this.blockStorage)
    //   this.blockType = 'title'
    //   this.inputValue = ''
    // }
  }
}
</script>

<style>
  .avatar {
    display: flex;
    justify-content: center;
  }

  .avatar img {
    width: 150px;
    height: auto;
    border-radius: 50%;
  }
</style>

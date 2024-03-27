<template>
  <div class="container column">
    <app-left-card @submit-handler="transferToRight"></app-left-card>
    <app-right-card
    :rightStorage="generalStorage"
    ></app-right-card>
  </div>
  <div class="container">
    <p>
      <app-button
      :btnType="'button'"
      @load="loadComments"
      >Загрузить комментарии</app-button>
    </p>
    <app-comments
    v-if="showComments"
    :commentsList="comments"
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
      showComments: false,
      comments: [],
      generalStorage: [],
      errors: [],
      urlComments: 'https://jsonplaceholder.typicode.com/comments?_limit=42'
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
    transferToRight (data) {
      this.generalStorage.push(data)
      console.log(this.generalStorage)
    },
    async loadComments () {
      try {
        this.loader = true
        const response = await fetch(this.urlComments)
        const result = await response.json()
        this.comments.push(...result)
        console.log(this.comments)
        this.showComments = true
        this.loader = false
      } catch (error) {
      // this.errors.push(error)
        console.log(error)
        this.loader = false
      }
    }
  },
  async mounted () {
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

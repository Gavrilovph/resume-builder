<template>
  <form class="card card-w30" @submit.prevent="submit">
    <div class="form-control">
      <label for="type">Тип блока</label>
      <select id="type" v-model="blockType" >
        <option value="title">Заголовок</option>
        <option value="subtitle">Подзаголовок</option>
        <option value="avatar">Аватар</option>
        <option value="text">Текст</option>
      </select>
    </div>

    <div class="form-control">
      <label for="value">Значение</label>
      <textarea
      id="value"
      rows="3"
      v-model="inputValue"
      ></textarea>
    </div>
    <app-button
    :disabled="inputValue.length < 3"
    >Добавить</app-button>
  </form>
</template>

<script>
import AppButton from './AppButton'

export default {
  data () {
    return {
      inputValue: '',
      blockType: 'title'
    }
  },
  emits: ['submit-handler'],
  methods: {
    submit () {
      this.$emit('submit-handler')
    }
    // submitHandler () {
    //   this.blockStorage.push({ type: this.blockType, value: this.inputValue })
    //   console.log(this.blockStorage)
    //   this.blockType = 'title'
    //   this.inputValue = ''
    // }
  },
  components: {
    'app-button': AppButton
  }
}
</script>

<style lang="scss" scoped>

</style>

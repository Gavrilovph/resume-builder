<template>
  <form class="card card-w30" @submit.prevent="submitHandler">
    <div class="form-control">
      <label for="type">Тип блока</label>
      <select id="type" v-model="blockType">
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
      v-model.trim="textValue"
      ></textarea>
    </div>
    <app-button
    :btnType="'submit'"
    :disabled="textValue.length < 3"
    >Добавить</app-button>
  </form>
</template>

<script>
import AppButton from './AppButton'

export default {
  emits: [
    'submit-handler'
  ],
  data () {
    return {
      textValue: '',
      blockType: 'title'
    }
  },
  methods: {
    submitHandler () {
      this.$emit('submit-handler', {
        block: this.blockType,
        text: this.textValue
      })
      this.blockType = 'title'
      this.textValue = ''
    }
  },
  components: {
    'app-button': AppButton
  }
}
</script>

<style lang="scss" scoped>

</style>

<template>
  <div class="divForm">
    <form @submit.prevent>
      <input
          v-model="post.title"
          class="inputForm"
          type="text"
          placeholder="Название"
      >
      <input
          v-model="post.body"
          class="inputForm"
          type="text"
          placeholder="Описание"
      >
      <button
          class="btn"
          @click="createPost"
      >Добавить</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "PostForm",

  data() {
    return {
      post: {
        title: '',
        body: '',
      }
    }
  },

  methods: {
    createPost() {
      this.post.id = Date.now()
      this.$emit('create', this.post)
      this.post = {
        title: '',
        body: '',
      }
    },
  },
}
</script>

<style lang="sass">
.divForm
  width: 100%

  form
    box-sizing: border-box
    display: grid
    grid-gap: 10px

.inputForm
  border: 1px solid teal
  padding: 10px 10px

.btn
  width: 30%
  padding: 10px 15px
  margin-top: 5px
  border: 1px solid teal
  background: none
  color: teal

  &:hover
    background: teal
    color: white
</style>
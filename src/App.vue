<template>
  <div class="wrapper">
    <div class="divForm">
      <form action="">
        <input
            :value="titlePost"
            class="inputForm"
            type="text"
            placeholder="Название"
        >
        <input
            :value="bodyPost"
            class="inputForm"
            type="text"
            placeholder="Описание"
        >
        <button class="btn" @click="createPost">Добавить</button>
      </form>
    </div>

    <div
        class="post"
        v-for="post in posts"
        key="post.id"
    >
      <div><strong>Название: </strong>{{ post.title }}</div>
      <div><strong>Описание: </strong>{{ post.body }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",

  data() {
    return {
      titlePost: '',
      bodyPost: '',
      posts: [
        {
          id: 1,
          title: 'Индексаторы (Indexers) в JavaScript',
          body: 'В некоторых современных объектно-ориентированных языках есть понятие идексаторов – свойств, позволяющих работать с экземпляром класса как с массивом, используя [] нотацию. В этой статье я хочу продемонстрировать как это сделать на современном JavaScript.'
        },
        {
          id: 2,
          title: 'Базовые задачи на Promise в JavaScript',
          body: 'Promise - специальный объект, который хранит своё состояние и используется для обработки результатов асинхронных операций.'
        },
        {
          id: 3,
          title: 'Стилизация однофайловых Vue компонентов',
          body: 'Если у вас есть опыт написания однофайловых Vue компонентов, вы, вероятно, сталкивались с написанием CSS в своем компоненте. Они позволяют разработчикам группировать код более логическими способами, а не разбивать компоненты по используемому языку (HTML, CSS или JavaScript).'
        },
        {
          id: 4,
          title: 'Создание веб-компонентов с помощью Vue 3.2',
          body: 'Вы когда-нибудь работали над несколькими проектами и хотели иметь набор настраиваемых компонентов, которые можно было бы использовать во всех из них?'
        },
      ]
    }
  },

  methods: {},
}
</script>

<style lang="sass">
body
  width: 80%
  border: 0
  margin: 0 auto
  box-sizing: border-box

.wrapper
  width: 100%
  padding: 20px

.divForm
  width: 100%
  form
    box-sizing: border-box
    display: grid
    grid-gap: 10px

.post
  margin-top: 15px
  padding: 15px
  border: 2px solid teal

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
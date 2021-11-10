<template>
  <div class="wrapper">
    <PostForm
        @create="addPost"
    />

    <PostList
        :posts="posts"
    />
  </div>
</template>

<script>
import PostList from "@/components/PostList";
import PostForm from "@/components/PostForm";

export default {
  name: "App",

  components: {
    PostList,
    PostForm,
  },

  data() {
    return {
      posts:     [
        {
          id:    1,
          title: 'Индексаторы (Indexers) в JavaScript',
          body:  'В некоторых современных объектно-ориентированных языках есть понятие идексаторов – свойств, позволяющих работать с экземпляром класса как с массивом, используя [] нотацию. В этой статье я хочу продемонстрировать как это сделать на современном JavaScript.'
        },
        {
          id:    2,
          title: 'Базовые задачи на Promise в JavaScript',
          body:  'Promise - специальный объект, который хранит своё состояние и используется для обработки результатов асинхронных операций.'
        },
        {
          id:    3,
          title: 'Стилизация однофайловых Vue компонентов',
          body:  'Если у вас есть опыт написания однофайловых Vue компонентов, вы, вероятно, сталкивались с написанием CSS в своем компоненте. Они позволяют разработчикам группировать код более логическими способами, а не разбивать компоненты по используемому языку (HTML, CSS или JavaScript).'
        },
        {
          id:    4,
          title: 'Создание веб-компонентов с помощью Vue 3.2',
          body:  'Вы когда-нибудь работали над несколькими проектами и хотели иметь набор настраиваемых компонентов, которые можно было бы использовать во всех из них?'
        },
      ]
    }
  },

  methods: {
    addPost(post) {
      this.posts.push(post)
    },
  },
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
</style>
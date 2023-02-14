<template>
  <h2>To-do-list만들기</h2>
  <input type="text" v-model="content" @keyup.enter="addToDo()" />
  <button @click="addToDo()">제출</button>
  <todolist :todos="todos" />
  <!-- 컴포넌트 데이터끌어오기 -->
</template>

<script>
import todolist from '../components/todolist.vue'
/* eslint-disable */
export default {
  name: 'app',
  data() {
    return {
      todos: [],
      content: ''
    }
  },
  methods: {
    addToDo: function () {
      console.log('성공')
      this.todos.push(this.content)
      this.content = ''
    }
  },
  components: {
    todolist
  }
}
</script>

<style></style>

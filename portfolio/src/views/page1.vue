<template>
  <h2>To-do-list만들기</h2>
  <input type="text" v-model="content" @keyup.enter="addToDo()" />
  <button @click="addToDo()">제출</button>
  <button @click="allclear()">전체삭제</button>
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
      content: '',
      num: 0
    }
  },
  created() {
    if (localStorage.length > 0) {
      for (let i = 0; i < localStorage.length; i++) {
        if (localStorage.key(i) !== 'loglevel:webpack-dev-server') {
          this.todos.push(localStorage.getItem(localStorage.key(i)))
        }
      }
    }
  },
  methods: {
    addToDo() {
      this.todos.push(this.content)
      console.log('성공')
      if (this.content !== '') {
        let value = this.content
        localStorage.setItem(this.content, JSON.stringify(value))
        this.content = ''
      }
    },
    allclear() {
      localStorage.clear()
      this.todos = []
    }
  },
  components: {
    todolist
  }
}
</script>

<style></style>

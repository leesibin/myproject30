<template>
  <h2>To-do-list만들기</h2>
  <input type="text" v-model="content" @keyup.enter="addToDo()" />
  <button @click="addToDo()">제출</button>
  <button @click="allclear()">전체닫기</button>

  <li id="text" v-for="list in todos" :key="list">
    <input type="checkbox" v-bind:id="checkd" />
    <label v-bind:for="checkd"></label>
    {{ list }} <button>닫기</button>
  </li>
  <!-- 컴포넌트 데이터끌어오기 -->
</template>

<script>
/* eslint-disable */
export default {
  name: 'app',
  data() {
    return {
      todos: [],
      content: ''
    }
  },
  created() {},
  methods: {
    addToDo() {
      console.log('성공')
      this.todos.push({ item: this.content })
      this.content = ''
      localStorage.setItem('ToDolist', JSON.stringify(this.todos))
    },
    allclear() {
      console.log('성공')
      this.todos = ''
      localStorage.clear()
    }
  }
}
</script>

<style></style>

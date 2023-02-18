<template>
  <h2>To-do-list만들기</h2>
  <input
    type="text"
    v-model="content"
    @keyup.enter="addToDo()"
    placeholder="입력하세요"
  />
  <button @click="addToDo()">제출</button>
  <button @click="allclear()">전체삭제</button>
  <ul>
    <li id="text" v-for="(todo, index) in todos" v-bind:key="todo">
      <input type="checkbox" v-bind:id="check" />
      <label v-bind:for="check"></label>
      <!--label 안해주며 동시에 체크 해진다  -->
      <span>{{ todo }}</span>
      <button @click="close(todo, index)">닫기</button>
    </li>
  </ul>
  <!-- 컴포넌트 데이터끌어오기 -->
</template>

<script>
/* eslint-disable */
export default {
  name: 'app',
  data() {
    return {
      todos: [],
      check: false,
      content: ''
    }
  },
  created() {
    const f5 = JSON.parse(localStorage.getItem('todolist')) ?? 0
    console.log(f5)
    if (f5) {
      f5.forEach((v) => {
        this.todos.push(v)
      })
    }
  },
  methods: {
    addToDo() {
      var obj = { item: this.content }
      this.todos.push(obj.item)
      localStorage.setItem('todolist', JSON.stringify(this.todos))
      this.content = ''
    },
    allclear() {
      localStorage.clear()
      this.todos = []
    },
    close(todos) {
      this.todos.pop(todos)
      localStorage.setItem('todolist', JSON.stringify(this.todos))
      console.log(todos)
    }
  }
}
</script>

<style>
#text {
  list-style: none;
}
</style>

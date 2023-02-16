<template>
  <div id="todolist">
    <ul>
      <li id="text" v-for="(todo, index) in todos" v-bind:key="todo.item">
        <input type="checkbox" />{{ todo }}
        <button @click="close(todo, index)">닫기</button>
      </li>
    </ul>
  </div>
</template>

<script>
/* eslint-disable */
export default {
  props: {
    todos: [] //props 자식데이터 부모에게 보내기
  },
  methods: {
    close(todo, index) {
      console.log(todo, index)
      localStorage.removeItem(todo.item)
      this.todos.splice(index, 1)
    }
  }
}
</script>

<style>
#text {
  list-style: none;
}
</style>

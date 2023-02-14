<template>
  <div id="todolist">
    <div id="container" v-for="data in todos" :key="data.id">
      <li id="text">{{ data }}</li>
    </div>
  </div>
</template>

<script>
/* eslint-disable */
export default {
  props: {
    todos: [] //props 자식데이터 부모에게 보내기
  },
  methods: {}
}
</script>

<style>
#text {
  list-style: none;
}
</style>

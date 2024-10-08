<template>
  <div id="app">
    <h1>To-Do List</h1>
    <TodoList />
  </div>
</template>

<script>
import TodoList from './components/TodoList.vue'

export default {
  name: 'App',
  components: {
    TodoList
  }
}
</script>

<style scoped>
#app {
  font-family: 'Anonymous Pro', monospace;
  color: #00ff00;
  background-color: #000000;
  text-align: center;
  padding: 20px;
}
</style>

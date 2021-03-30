<template>
  <div id="app">
    <div class="header">
          <AddTodo @added-todo="addedNew"/>
    </div>
      <ListTodos 
      :todos="todos" 
      @completed-index="markCompleted" 
      @deleted-index="deleteTodo"
      />
  </div>
</template>






<script>

import ListTodos from './components/ListTodos'
import AddTodo from './components/AddTodo'

export default {
  name: 'App',
  components: {
    ListTodos,
    AddTodo
  },
    data: () => ({
        todos: []
    }),
    methods: {
      addedNew(todo) {
        this.todos.push(todo);
      },
      markCompleted(index) {
        this.todos[index].comleted = !this.todos[index].comleted;
        console.log("checked");
      },
      deleteTodo(index) {
        this.todos.splice(index,1);
      }
    }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

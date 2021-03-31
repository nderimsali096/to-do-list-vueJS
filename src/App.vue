<template>
  <div id="app">
    <div class="header">
      <p>dasdasd</p>
      <p>dasdasd</p>
      <HelloWorld/>
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

import HelloWorld from './components/HelloWorld'
import ListTodos from './components/ListTodos'
import AddTodo from './components/AddTodo'

export default {
  name: 'App',
  components: {
    ListTodos,
    AddTodo,
    HelloWorld
  },
    data: () => ({
        todos: []
    }),
    methods: {
      addedNew(todo) {
        this.todos.push(todo);
      },
      markCompleted(index) {
        this.todos[index].completed = !this.todos[index].completed;
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
  background-color: #0093E9;
  background-image: linear-gradient(160deg, #0093E9 0%, #80D0C7 100%);
  height: 100vh;
  margin: 0;
}
p {
  opacity: 0;
}
</style>

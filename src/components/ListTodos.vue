<template>
  <div class="container">
    <div class="row">
      <div class="col-12">
        <ul class="list-group">
          <Todo 
          v-for="(todo, index) in todos" 
          :key="index" 
          :todo="todo" 
          @completed="completed(index)" 
          @deleted="deleted(index)"/>
        </ul>
      </div>
    </div>
  </div>
</template>



<script>
import Todo from './Todo'
export default {
  name: 'ListTodos',
  components : {
      Todo
  },
  props: {
      todos: Array
  },
  methods: {
      completed (index) {
          this.$emit('completed-index', index);
      },
      deleted (index) {
          this.$emit('deleted-index', index);
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>

<template>
    <li class="d-flex list-group-item">
      <button 
        class="btn border-0 flex-grow-1 text-left shadow-none"
        :class="{ 'checked': todo.completed }"
        @click="completeTodo"  
      > {{todo.text }} </button>
      <button 
        v-on:click="deleteTodo"
        class="btn btn-outline-danger border-0"
      > <span class="fa fa-trash">&#10005;</span>
      </button>
    </li>   
</template>



<script>
export default {
  name: 'Todo',
  
  props: {
      todo: Object
      
  },

  methods: {
      completeTodo () {
          this.$emit('completed');
      },
      deleteTodo: function() {
          this.$emit('deleted');
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.checked {
    text-decoration: line-through;
}
</style>

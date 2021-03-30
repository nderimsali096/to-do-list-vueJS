<template>
  <div class="d-flex justify-content-center">
    <form class="col-md-8 d-flex"
      @submit.prevent="addNew">
        <input 
        v-model="message"
        type="text"
        class="form-control input" 
        placeholder="Add a new todo... " 
        required
        >
        <button class="btn btn-primary" type="submit">Add</button>
      </form>
  </div>
</template>



<script>
export default {
  name: 'AddTodo',
    data: () => ({
        message: '',
    }),
  methods: {
      addNew: function() {
          if (this.message !== '') {
            const newTodo = {
               text: this.message,
               completed: false
           }
           this.message = '';
           this.$emit('added-todo', newTodo);
          }
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  div {
    margin-bottom: 3rem;
  }

  .input {
    margin-right: 1rem;
  }
 </style>

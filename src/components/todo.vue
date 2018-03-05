<template lang="pug">
  .todo
    todo-input(@addTodo="addNewTodo")
    todo-list(
      :todos="todos",
      @checkTodo="checkTodo")
    
</template>


<script>
  import todoInput from './todoInput'
  import todoList from './todoList'
  
  export default {
    data: () => ({
      todos: []
    }),
    components: {
      todoInput,
      todoList
    },
    methods: {
      addNewTodo(todo) {
        this.todos.push(todo);
      },
      checkTodo(todo) {
        this.todos = this.todos.map(item => item.id === todo.id ? todo : item)
      }
    }
  }
</script>

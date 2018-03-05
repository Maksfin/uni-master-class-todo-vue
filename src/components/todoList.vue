<template lang="pug">
  .todo-list(v-if="todos.length")
    .content
        ul.list
            li.item(v-for="todo in todos")
                todo-item(
                    :todo="todo",
                    @checkTodo="checkTodo"
                )
    .footer
        .footer-content
            .counter  Кол-во: {{todos.length}}
        .filter
            button(type="button") Все
            button(type="button") Активные
            button(type="button") Завершенные
</template>

<script>
    import todoItem from './todoItem'
    export default {
        props: {
            todos: Array
        },
        components: {
           todoItem 
        },
        methods: {
            checkTodo(todo) {
                this.$emit("checkTodo", todo)
            }
        }
    }
</script>

<style lang="scss" src="styles/todoList.scss">
    
</style>


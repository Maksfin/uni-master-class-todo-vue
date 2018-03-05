<template lang="pug">
    .todo-item
        label.label(:class="{checked: todo.checked}")
            .input-block
                input(
                    type="checkbox"
                    @change="checkTodo"
                ).input
            .title {{todo.name}}
            .button
                button(type="button") x
</template>

<script>
export default {
  props: {
      todo: Object
  },
  methods: {
    checkTodo(e) {
        const todoItem = {
            ...this.todo,
            checked: e.target.checked
        }

        this.$emit("checkTodo", todoItem)
    }
  }
}
</script>

<style lang="scss" src="styles/todoItem.scss">
</style>




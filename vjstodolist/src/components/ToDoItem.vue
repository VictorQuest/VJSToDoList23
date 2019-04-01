<template>
  <div class="todo-item">
    {{todo.title}}
  </div>
  <div class="remove-item" @click="removeTodo(index)">
    &times;
  </div>

</template>

<script>
export default {
  name: 'todo-item',
  props:{
    todo: {
      type: Object,
      required: true,
    },
    index: {
      type: Number,
      required: true,
    }
  }
}
</script>

<style lang="css" scoped>
</style>

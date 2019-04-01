<template>
<div>
  <input type="text" class="todo-input" placeholder="Enter HERE the tasks that need to be done" v-model="newTodo" @keyup.enter="addTodo">
  <todo-item v-for="(todo,index) in todos" :key="todo.id">
    <!-- <div>
      {{todo.title}}
    </div>
    <div class="remove-item" @click="removeTodo(index)">
      &times;
    </div> -->
  </div>
</div>
</template>

<script>
import ToDoItem from './ToDoItem'


export default {
  name: 'todo-list',
  components: {
    ToDoItem,
  },
  data() {
    return {
      newTodo: '',
      idForTodo: 3,
      todos: [{
          'id': 1,
          'title': 'Fishing in Sweden',
          'completed': false,
        },
        {
          'id': 2,
          'title': 'Take over FrontEnds World',
          'completed': false,
        },
      ]
    }
  },
  methods: {
    addTodo() {
      //if (this.newTodo.trim().length = 0) {
        //return
      //}
      this.todos.push({
        id: this.idForTodo,
        title: this.newTodo,
        completed: false,
      })
      this.newTodo = ''
      this.idForTodo++
    },
    removeTodo(index){
      this.todos.splice(index, 1)
    }
  }
}
</script>

<style lang="scss">
.todo-input {
    width: 100%;
    padding: 10px 18px;
    font-size: 18px;
    margin-bottom: 16px;
}

.todo-item {
    margin-bottom: 12px;
    display: flex;
    align-items: center;
    justify-content: space-between;
}
.remove-item {
    cursor: crosshair;
    margin-left: 14px;
    &:hover {
        color: rgb(242, 24, 37);
    }
}
</style>

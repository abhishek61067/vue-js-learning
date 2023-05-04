<script>
// give each todo a unique id
let id = 0

export default {
  name:"ListRender",
  data() {
    return {
        // state defined inside the data() option are reactive
      newTodo: '',
      todos: [
        { id: id++, text: 'Learn HTML' },
        { id: id++, text: 'Learn JavaScript' },
        { id: id++, text: 'Learn Vue' }
      ]
    }
  },
  methods: {
    addTodo() {
      this.todos.push({ id: id++, text: this.newTodo })
      this.newTodo = ''
    },
    removeTodo(id) {
      this.todos = this.todos.filter((t) => t.id !== id)
    }
  }
}
</script>

<template>
    <p class="text-primary h2" >List rendering</p>
  <form @submit.prevent="addTodo">
    <input v-model="newTodo">
    <button>Add Todo</button>    
  </form>
  <ul>
    <li v-for="todo in todos" :key="todo.id">
      {{ todo.text }}
      <button @click="removeTodo(todo.id)">X</button>
    </li>
  </ul>
</template>
<script>
let id = 0

export default {
  data() {
    return {
      newTodo: '',
      hideCompleted: false,
      todos: [
        { id: id++, text: 'Learn HTML', done: true },
        { id: id++, text: 'Learn JavaScript', done: true },
        { id: id++, text: 'Learn Vue', done: false }
      ],
      tests:[],
           
    }
  },  
  computed: {
    // test(){
    //   alert("test");
    // },
    testC(){
alert("ComputedVue.vue: function inside computed property doesnot require () to be included when it is invoked from template");
    },
    filteredTodosC() {
      let testC = this.hideCompleted
        ? this.todos.filter((t) => !t.done)
        : this.todos
        alert(`ComputedVue.vue: function inside the computed will run for the first time. But after it, if you try to invoke the funciton inside computed, it wont get executed until and unless the dependency is not changed. Try to input something and click on add todo button to see the result. The result is:
        After tests is changed, template is rerendering. Now if you observe, testM() is executing but testM is not because when we are clicking add todo, tests is getting changed which is not the dependency of testC. See the template for more understanding.
        `)
    },
    toggleHideCompleted(){
      this.hideCompleted = !this.hideCompleted;
    },
    // test(){
    //   alert("test");
    // }
    
  },
  methods: {
    testM(){
alert("ComputedVue.vue: function inside methods property require () to be included when it is invoked from template");
    },
         filteredTodosM() {
      let testM =  this.hideCompleted
        ? this.todos.filter((t) => !t.done)
        : this.todos
    },
    // if you add toggleHideCompleted to computed, it will run for the first time but it wont run for the second time if its dependency is not changed.
     
    addTodo() {
      this.todos.push({ id: id++, text: this.newTodo, done: false })
      this.newTodo = ''
    },
    addTodos() {
      this.tests.push({ id: id++, text: this.newTodo, done: false })
      this.newTodo = ''
    },
    removeTodo(todo) {
      this.todos = this.todos.filter((t) => t !== todo)
    }
  }
}
</script>

<template>
    <div class="text-primary h2">Computed:{{ testM() }}</div>
    <div class="text-primary h2">hideCompleted:{{ hideCompleted }}</div>
    <!-- function inside the computed will only run when the dependecies of function inside computed will change -->
    <div class="text-primary h2">Computed:{{ testC }}</div>
    <div class="text-secondary h4">Function inside computed property will be triggered when its dependencies changes. In our case, when we click on add todo, this.todos is changed, now template is rerendered again and also filteredTodosF is returning us the updated value since, filteredTodosF(function inside computed which is dependent to this.toDos) was executed when it dependencies(this.todos) was changed.</div>
    <p class="text-secondary">You are not able to hide completed because you are actually using the list inside of data option and not the function inside computed.</p>
  <form @submit.prevent="addTodos">
    <input v-model="newTodo">
    <button>Add Todo</button>
  </form>
  <ul>
    <li v-for="todo in filteredTodosC" :key="todo.id">
      <input type="checkbox" v-model="todo.done">
      <span :class="{ done: todo.done }">{{ todo.text }}</span>
      <button @click="removeTodo(todo)">X</button>
    </li>
  </ul>
  <!-- <button @click="this.hideCompleted = !this.hideCompleted"> -->
  <button @click="toggleHideCompleted">
    {{ hideCompleted ? 'Show all' : 'Hide completed' }}
  </button>
</template>

<style>
.done {
  text-decoration: line-through;
}
</style>
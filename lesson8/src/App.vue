<script>
import TodoList from './TodoList.vue'
export default {
  components: {
    TodoList
  },
  data(){
    return {
      todos: [
        { id: 1, name: "todo item", done: false },
        { id: 2, name: "todo item 2", done: false },
        { id: 3, name: "todo item 3", done: true },
        { id: 4, name: "todo item 4", done: false },
        { id: 5, name: "todo item 5", done: true },
      ]
    }
  },
  methods:{
    addFakeRecord(){
      this.todos.push({ id: 5, name: "todo", done: true })
    }
  },
  computed: {
    filteredTodos(){
      return this.todos.filter(item => item.done === true)
    },
    activeTodos(){
      return this.todos.filter(item => item.done === false)
    },
    listLength(){
      return this.todos.length
    }
  },
  watch: {
    listLength(n, o){
      console.log(n, 'aqamde iyo ' + o)
    }
  },
  mounted(){
    // console.log("App Component Mounted")
  }
}
</script>
<template>
  <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" @click.prevent="addFakeRecord">Add New One</button>
  <h2>{{ listLength }}</h2>
  <h1>All Items</h1>
  <TodoList :data="todos" />
  <h1>Done</h1>
  <TodoList :data="filteredTodos" />
  <h1>Active</h1>
  <TodoList :data="activeTodos" />
</template>
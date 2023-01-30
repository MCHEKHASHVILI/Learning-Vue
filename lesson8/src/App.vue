<script>
import TodoList from './TodoList.vue'
import TodoItemForm from './components/TodoItemForm.vue'

export default {
  components: {
    TodoList,
    TodoItemForm,
  },
  data(){
    return {
      todos: [
        { id: 1, name: "todo item", done: false },
        { id: 2, name: "todo item 2", done: false },
        { id: 3, name: "todo item 3", done: false }
      ],
    }
  },
  methods:{
    putNewItemIntoTodosList(data){
      this.todos.push({
        id: this.nextId,
        name: data,
        done: false
      })
    },
    changeStatus(record){
      let v = this.todos.find(item => item.id === record.id)
      v.done = !v.done
    },
    deleteItemFromTodoList(record){
      let v = this.todos.find(item => item.id === record.id)
      this.todos.splice(this.todos.indexOf(v), 1)
    }
  },
  computed: {
    nextId(){
      return this.todos.length + 1
    },
    activeTodos(){
      return this.todos.filter(value => value.done === false)
    },
    doneTodos(){
      return this.todos.filter(value => value.done === true)
    },
  },
  watch: {
    //  ...
  },
  mounted(){
    // ...
  }
}
</script>
<template>
  <div class="container">
    <div class="todos">
      <TodoItemForm @onSubmitCustom="putNewItemIntoTodosList($event)"/>
      <h2> All Todo items </h2>
      <TodoList :data="todos" />

      <h2>Avtive Todos</h2>
      <TodoList :changeStatus="true" :data="activeTodos" @onChangeDoneStatus="changeStatus($event)" />
      
      <h2>Todos with Done Status</h2>
      <TodoList :canDelete="true" :data="doneTodos" @onDelete="deleteItemFromTodoList($event)"/>
    </div>
    <div class="filter">
      <input type="text" />
      <TodoList :data="todos" />
    </div>
  </div>
</template>
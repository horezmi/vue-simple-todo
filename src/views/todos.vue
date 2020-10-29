<template>
  <div>
    <h2>Todos Page</h2> 
    <p>Home in next link</p>
    <router-link to="/" class="home-link">Todos</router-link>
    <hr>
    <addTodo 
      @add-todo="addTodo"
    />
    <hr>
    <todoList 
      v-if='todos.length'
      v-bind:todos="todos"
      @remove-todo="removeTodo"
    />
    <p v-else>No todos</p>
  </div>
</template>

<script>
import todoList from '@/components/todoList' 
import addTodo from '@/components/addTodo' 

export default {
  name: 'App',
  data() {
    return {
      todos: [
        {id: 1, title: 'Create a web application', completed: false},
        {id: 2, title:'Go for an interview', completed: false},
        {id: 3, title: 'Get an offer', completed: false},
      ]
    }
  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter(t => t.id !== id)
    },
    addTodo(todo) {
      this.todos.push(todo)
    },
  },
  components: {
    todoList, addTodo
  },
}
</script>

<style scoped>
  .home-link {
    text-decoration: none;
  }
</style>
<template>
  <div id="app">
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Todos from './components/Todos.vue'

export default {
  name: 'app',
  components: {
    Todos
  },
  data(){
    return {
      todos: [
        {
          id: 1,
          title: "todo one",
          completed: false
        },
        {
          id: 2,
          title: "todo two",
          completed: true
        },
        {
          id: 3,
          title: "todo three",
          completed: false
        }
      ]
    }
  },
  methods: {
    deleteTodo(id){
      this.todos = this.todos.filter (todo => todo.id !== id);
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body{
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}

</style>

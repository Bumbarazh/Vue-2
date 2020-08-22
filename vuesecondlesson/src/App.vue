<template>
  <div id="app">
    <AddTodo 
    :toDos='toDos'
    @updateTodos='updateTodos'
    />
    <TodoList 
    :toDos='toDos'
    @remWhatTodo='remWhatTodo'
    />
  </div>
</template>

<script>
import AddTodo from "@/components/AddTodo";
import TodoList from "@/components/todolist/TodoList";

export default {
  name: 'App',

  components: {
    AddTodo,
    TodoList,

  },

  data () {
    return {
      toDos: [],
      index: 0
    }
  },

  methods: {
    updateTodos: function(event) {
      this.toDos.push(event);
    },

    remWhatTodo: function (el) {
      this.index = this.toDos.indexOf(el);
      this.toDos = this.toDos.filter((el, i)  => i !== this.index);
    }
  }
  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

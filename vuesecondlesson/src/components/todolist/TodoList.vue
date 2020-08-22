<template>
  <div id="todolist">
          <TodoItem
           v-for="(toDo, i) in toDos" 
           :key="i"
           :todo='toDo'
           @removeTheTodo='removeTheTodo'
           />
  </div>
</template>

<script>
import TodoItem from "@/components/todolist/TodoItem";

export default {
    name: 'TodoList',

    props: {
        toDos: {
        type: Array,
        required: true
        }
        
    },

    components: {
        TodoItem,

    },

    data () {
        return {

        }
    },

    methods: {
        removeTheTodo: function(event) {
            this.$emit('remWhatTodo', event);
        }
    }
    
}
</script>>
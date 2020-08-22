<template>
  <div id="addtodo">
    <input type="text" v-model="textOfTodo">
    <button v-if="textOfTodo.length <= 10" @click="addToTodos">Add Your Todo</button>
  </div>
</template>

<script>
export default {
    name: 'AddTodo',

     props: {
        toDos: {
        type: Array,
        required: true
        }
        
    },

    data () {
        return {
            textOfTodo: '',
        }
    },

    methods: {
        addToTodos: function () {
            this.$emit('updateTodos', this.textOfTodo)
        }
    }
    
}
</script>>
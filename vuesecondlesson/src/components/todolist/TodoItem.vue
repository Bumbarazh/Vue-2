<template>
  <div id="todoitem">
    <span>
        {{todo}}
        <button
        @click="removeToDo"
        >Remove
        </button>
    </span>
  </div>
</template>

<script>
export default {

    props: {
        todo: {
        type: String,
        required: true
        }
        
    },

    name: 'TodoItem',

    data () {
        return {

        }
    },

    methods: {
        removeToDo: function () {
            this.$emit('removeTheTodo', this.todo);  
        }
    }
     
}
</script>>
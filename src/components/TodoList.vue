<template>
<div>
  <Todo 
        v-for="(todo, i) in todos" 
        :key="i"
        :todo="todo" 
        @toggle-checkbox="toggleCheckbox"
        @click-delete="deleteTodo"
   />
   </div>
</template>

<script>
import Todo from '@/components/Todo.vue';

export default {
    components: {
        Todo
    },
    computed: {
        todos() {
            return this.$store.state.todos;
        }
    },
    methods: {
        toggleCheckbox(e) {
            this.$emit('toggle-checkbox', e.target.value)
        },
        deleteTodo(todoId) {
            this.$emit('click-delete', todoId)
        }
    }

}
</script>

<style>

</style>
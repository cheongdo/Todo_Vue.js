<template>
<div id="app" class="container">
  <h1 class="text-center" :class="'text-muted'">Todo App</h1>
  <input 
  v-model="todoText"
  type="text" 
  class="w-100 p-2" 
  placeholder="Type todo"
  @keyup.enter="addTodo"
  >
  <hr>
  <Todo 
  v-for="todo in todos" 
  :key="todo.id"
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
  data() {
    return {
      todoText: '',
      todos: [
        { id: 1, text: 'buy a maset', checked: false},
        { id: 2, text: 'buy a house', checked: false}
      ]
    }
  },
  methods: {
    deleteTodo(id) {
      // const index = this.todos.findIndex(todo => {
      //   return todo.id === id;
      // });
      // this.todos.splice(index, 1);
      this.todos = this.todos.filter(todo => todo.id !== id)
    },
    addTodo(e) {
        this.todos.push({
          id: this.todos.length + 1,
          text: e.target.value,
          checked: false
        });
        this.todoText = '';
    },
    toggleCheckbox({id, checked}) {
      const index = this.todos.findIndex(todo => {
        return todo.id === id;
      });
      this.todos[index].checked = checked;
    }
  }
}

</script>

<style>

</style>

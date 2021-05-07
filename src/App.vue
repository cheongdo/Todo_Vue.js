<template>
<div id="app" class="container">
  <h1 class="text-center">Todo App</h1>
  <CompletedTodo />
  <AddTodo />
  <hr>
  <TodoList />
</div>
</template>

<script>
import TodoList from '@/components/TodoList.vue';
import CompletedTodo from '@/components/CompletedTodo.vue';
import AddTodo from './components/AddTodo.vue';

export default {
  components: {
    TodoList,
    CompletedTodo,
    AddTodo
  },
  data() {
    return {
      todoText: '',
      // todos: [
      //   { id: 1, text: 'buy a maset', checked: false},
      //   { id: 2, text: 'buy a house', checked: false}
      // ]
    }
  },
  methods: {
    // deleteTodo(id) {
    //   const index = this.todos.findIndex(todo => {
    //     return todo.id === id;
    //   });
    //   this.todos.splice(index, 1);
      // this.todos = this.todos.filter(todo => todo.id !== id)
    // },
    // addTodo(e) {
        // this.todos.push({
        //   id: this.todos.length + 1,
        //   text: e.target.value,
        //   checked: false
        // });
    //     this.todoText = '';
    // // },
    // toggleCheckbox({id, checked}) {
    //   const index = this.todos.findIndex(todo => {
    //     return todo.id === id;
    //   });
  //   //   this.todos[index].checked = checked;
  //   }
  // }
}
}

</script>

<style>

</style>

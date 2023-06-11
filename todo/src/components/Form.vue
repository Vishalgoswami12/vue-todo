<template>
    <div>
      <h2>Todo List</h2>
      <form @submit.prevent="addTodo">
        <input type="text" v-model="newTodo" placeholder="Enter a new todo" />
        <button type="submit">Add Todo</button>
      </form>
  
      <ul>
        <li v-for="(todo, index) in todos" :key="index">
          {{ todo }}
          <button @click="removeTodo(index)">Remove</button>
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  import { ref } from 'vue';
  
  export default {
    name: 'TodoList',
    setup() {
      const todos = ref([]);
      const newTodo = ref('');
  
      const addTodo = () => {
        if (newTodo.value.trim() !== '') {
          todos.value.push(newTodo.value);
          newTodo.value = '';
        }
      };
  
      const removeTodo = (index) => {
        todos.value.splice(index, 1);
      };
  
      return {
        todos,
        newTodo,
        addTodo,
        removeTodo,
      };
    },
  };
  </script>
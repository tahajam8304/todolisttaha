<template>
  <div>
    <h1>Todo List</h1>
    <form @submit.prevent="addTodo">
      <input v-model="newTodo" placeholder="Enter a task">
      <button>Add</button>
    </form>
    <ul>
      <li v-for="(todo, index) in todos" :key="index">
        {{ todo.text }}
        <button @click="deleteTodo(index)">Delete</button>
      </li>
    </ul>
  </div>
</template>

<script>


export default {
  data() {
    return {
      todos: [],
      newTodo: '',
    };
  },
  methods: {
    addTodo() {
      if (this.newTodo.trim()) {
        this.todos.push({ text: this.newTodo });
        this.newTodo = '';
      }
    },
    deleteTodo(index) {
      this.todos.splice(index, 1);
    },
  },
};
</script>

<style>
/* Add your custom styles here */
</style>
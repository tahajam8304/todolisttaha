<template>
  <div>
    <h1 class="ww">Todo List</h1>
    <form @submit.prevent="addTodo">
      <input v-model="newTodo" placeholder="Enter a task" class="container">
      <button>Add</button>
    </form>
      <ul class="border">
         <li v-for="(todo, index) in todos" :key="index">
          <label class="containers">
                <input type="checkbox">
               <span class="checkmark"></span>
          </label>
          {{ todo.text }}
        <button @click="deleteTodo(index)">DELE</button>
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

body{
  background-color: black;

}

ul{
  width: 100px;
  height: 100px;
  /* flex: content; */
  align-content: center;
  align-items: center;
  list-style-type: none;
  margin-left: 700px;
  padding-left: 45%;
  padding-top: 50px;
  /* display: ; */
  /* text-decoration: none;
  padding: 5px; */
  margin: 5px;
  display: inline;
}
li{
  
  /* border-bottom: 1px white solid; */
  /* border-radius: 5px; */
  color: white;
  text-decoration: none;
  padding-top: 10px;
  
}
.ww{
  color: red;
}

button{
  background-color: blue;
  color: white;
  border: 2px solid black;
  border-radius: 5px;
  box-shadow: 5px;
  width: 50px;
  height: 35px;

}
button:hover{
  background-color: red;
  transition: 0.7s;
}

.container{
  height: 30px;
  width: 30%;
  border: blue solid 2px;
  border-radius: 5px;
  color: red;
  
}




</style>
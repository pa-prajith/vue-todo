<template>
<div id="container">
  <header>
    <h1>Todo Application</h1>
  </header>
  <section class="form-container">
    <form action="">
      <input type="text" placeholder="Enter Todo item">
      <button>Add Todo</button>
    </form>
  </section>
  <section class="todoList">
    <ul>
      <li>
        <div class="todo-item">Todo Item List goes here</div>
        <div class="icons">
          <i class="far fa-check-circle"></i>
          <i class="far fa-edit"></i>
          <i class="fas fa-trash"></i>
        </div>
      </li>
      <li>
        <div class="todo-item done">Todo Item List goes here. Content goes here. This is a long text!!!. Now what , lets see how it looks on page </div>
        <div class="icons">
          <i class="far fa-check-circle"></i>
          <i class="far fa-edit"></i>
          <i class="fas fa-trash"></i>
        </div>
      </li>
      <li>
        <div class="todo-item">Todo Item List goes here</div>
        <div class="icons">
          <i class="far fa-check-circle"></i>
          <i class="far fa-edit"></i>
          <i class="fas fa-trash"></i>
        </div>
      </li>
    </ul>
  </section>
</div>

</template>

<script>

import { ref } from 'vue';

export default {
  name: 'App',
  setup() {
    const newList = ref('');
    const todoArray = ref([]);
    
    return {
      newList,
      todoArray
    }
  }
}

</script>

<style>
#container {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}

/* header */
header {
  text-align: center;
}

/* form-container */
.form-container {
  width: 75%;
  padding: 50px;
  margin: 0 auto;
  text-align: center;
}

.form-container input {
  width: 50%;
  margin-right: 30px;
  height: 30px;
  padding: 10px;
  border: 1px solid #2c3e50;
  border-radius: 15px;
  font-weight: 500;
  font-size: 21px;
  outline: none;
  
}

.form-container button {
  padding: 13px 17px;
  background-color: #2c3e50;
  color: #ffffff;
  border-radius: 15px;
  font-weight: bold;
}

/* Todolist Container */
.todoList {
  width: 55%;
  padding: 50px;
  margin: 0 auto; 
  font-size: 25px;
}

.todoList ul li {
  list-style: none;
  display: flex;
  justify-content: space-between;
  padding: 20px;
  border-bottom: 1px solid #cccccc;
}

.done {
  text-decoration: line-through;
}

.todo-item {
  font-weight: 500;
}

.icons {
  white-space: nowrap;;
}

.icons i{
  margin-left: 15px;
  cursor: pointer;
}
</style>

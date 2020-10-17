<template>
<div id="todo-container">
  <header>
    <h1>Todo Application</h1>
  </header>
  <section class="todo-form">
    <form action="">
      <input type="text" placeholder="Enter Todo item">
      <button>Add Todo</button>
    </form>
  </section>
  <section class="todo-list">
    <ul>
      <li>
        <div class="todo-item">Todo Item List goes here</div>
        <div class="todo-icons">
          <i class="far fa-check-circle"></i>
          <i class="far fa-edit"></i>
          <i class="fas fa-trash"></i>
        </div>
      </li>
      <li>
        <div class="todo-item">Todo Item List goes here</div>
        <div class="todo-icons">
          <i class="far fa-check-circle"></i>
          <i class="far fa-edit"></i>
          <i class="fas fa-trash"></i>
        </div>
      </li>
      <li>
        <div class="todo-item">Todo Item List goes here</div>
        <div class="todo-icons">
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
#todo-container {
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

/* Form */
.todo-form {
  width: 75%;
  padding: 50px;
  margin: 0 auto;
  text-align: center;
}

.todo-form input {
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

.todo-form button {
  padding: 16px 21px;
  background-color: #2c3e50;
  color: #ffffff;
  border-radius: 15px;
  font-weight: bolder;
  position: relative;
  bottom: 3px;
}

/* Todolist  */
.todo-list {
  width: 55%;
  padding: 50px;
  margin: 0 auto; 
  font-size: 25px;
}

.todo-list ul li {
  list-style: none;
  display: flex;
  justify-content: space-between;
  padding: 20px;
  border-bottom: 1px solid #cccccc;
}

.todo-done {
  text-decoration: line-through;
}

.todo-item {
  font-weight: 500;
}

.todo-icons {
  white-space: nowrap;
}

.todo-icons i{
  margin-left: 15px;
  cursor: pointer;
}
</style>

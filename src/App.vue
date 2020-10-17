<template>
<div id="todo-container">
  <header>
    <h1>Todo Application</h1>
  </header>
  <section class="todo-form">
    <form @submit.prevent="submitHandler">
      <input type="text" v-model="newList" placeholder="Enter Todo item">
      <button v-if="action === 'edit'" type="submit">Update</button>
      <button v-else type="submit">Add</button>
      <button v-if="action === 'edit'" @click="cancelHandler">Cancel</button>
    </form>
  </section>
  <section class="todo-list">
    <ul>
      <li v-for="(todo,index) in todoArray" :key="todo.id">
        <div class="todo-item" :class="{'todo-done': todo.isDone}">{{todo.content}}</div>
        <div class="todo-icons">
          <i class="far fa-check-circle" @click="toggleDoneHandler(index)"></i>
          <i class="far fa-edit" @click="editHandler(index)"></i>
          <i class="fas fa-trash" @click="deleteHandler(index)"></i>
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
    const action = ref('');
    const editIndex = ref(0);

    const submitHandler = () => {
      if(newList.value.trim().length) {
        if(action.value === 'edit') {
          todoArray.value[editIndex.value].content = newList.value;
          action.value = '';
          editIndex.value = 0;
        } else {
          todoArray.value.push({
            id: Date.now(),
            content: newList.value,
            isDone: false
          });
        }
        newList.value = '';
      }
    };

    const toggleDoneHandler = index => {
      todoArray.value[index].isDone = !todoArray.value[index].isDone;
    };

    const editHandler = index => {
      action.value = 'edit';
      editIndex.value = index;
      newList.value = todoArray.value[index].content;
    };

    const cancelHandler = () => {
      action.value = '';
      editIndex.value = 0;
      newList.value = '';
    }

    const deleteHandler = index => {
      todoArray.value.splice(index, 1);
    };
    
    return {
      newList,
      todoArray,
      submitHandler,
      toggleDoneHandler,
      editHandler,
      deleteHandler,
      cancelHandler,
      action
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
  margin-left: 30px;
  outline: none;
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

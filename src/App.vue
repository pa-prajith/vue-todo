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
</div>

</template>

<script>

export default {
  name: 'App',
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
}

.form-container button {
  padding: 13px 17px;
  background-color: #2c3e50;
  color: #ffffff;
  border-radius: 15px;
  font-weight: bold;
}

</style>

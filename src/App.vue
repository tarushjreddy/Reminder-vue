<template>
<div class="container">
  <h1 class="main__header">Todo List Pro</h1>
  <Todo/>
  </div>
</template>

<script>
import Todo from "./components/todo.vue"
export default {
  name: "App",
  components : {
    Todo
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@500&display=swap');

.main__header{
  color: white;
  background-color: black;
   text-align: center;
  font-family: 'Poppins', sans-serif;

}
.container{
 display: flex;
 flex-direction: column;
   background-color: black;
 text-align: center;
 align-items: center;
 justify-content: center;
}
body{
    background-color: rgb(0, 0, 0);
}

</style>
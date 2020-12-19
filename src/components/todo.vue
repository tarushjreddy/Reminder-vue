<template>
<div class="container">
<h1>Programming is the best</h1>

<div class="row">
        <Adding @on-addtodo="addTodo($event)"/>
</div>
<div class="list_details">
  <ul>
  <Todos v-for="(todo, index) in todos" :key="index" :todoResult="todo.todoString" :completed="todo.completed" @on-delete="deleteTodos(todo)" @on-toggle="toggleTodos(todo)" @on-edit="editTodos(todo, $event)" >{{todo.todoString}} </Todos>
  </ul>
</div>

  </div>
</template>

<script>
import  Todos  from "./main.vue";
import Adding from "./new";

export default {
    components : {
    Todos,
        Adding
  },

  data() {
    return {
      todos: [
        {todoString: "Todo is being complted one", completed: false},
        {todoString: "Todo is being complted two", completed: false},
        {todoString: "Todo is being complted three", completed: false},
        {todoString: "Todo is being complted four", completed: false}
        
      ]
    };
  },
  methods: {
    addTodo(newTodo){
      this.todos.push({
        todoString: newTodo, completed: false
      })
    },
    editTodos(todo, newTodoString){
      todo.todoString = newTodoString;
    },
    toggleTodos(todo){
        todo.completed = !todo.completed;
    },
    deleteTodos(deleteTodos){
      this.todos = this.todos.filter(todo => todo.todoString !== deleteTodos.todoString)
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@500&display=swap');
  /* font-family: 'Poppins', sans-serif; */
.container{
  color: white;
  font-family: 'Poppins', sans-serif;
}
</style>
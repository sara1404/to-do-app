<template>
  <div class="container">
    <Header/>
    <ToDoBox :todos="todos" @createdToDo="addToDo" @removeToDo="removeToDo"/>
  </div>
</template>

<script>

import Header from "./components/Header.vue"
import ToDoBox from "./components/todo-box.vue"
import axios from "axios"

export default {
  components:{
    Header,
    ToDoBox,
  },
  data: function(){
    return {
      todos: [],
    }
  },
  methods:{
    addToDo: async function(obj){
      this.todos.unshift(obj);
      await axios.post('http://localhost:3000/todos', obj);
    },
    removeToDo: async function(id){
      this.todos = this.todos.filter((todo) => {return todo._id != id});
      await axios.delete('http://localhost:3000/todos/' + id);
    }
  },
  created: async function(){
      let resp = await axios.get('http://localhost:3000/todos');
      this.todos = resp.data.data.todos;
  }
}
</script>

<style>
  .container{
    height: 100%;
    width: 100%;
    background-color: #064866;
  }
</style>

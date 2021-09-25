<template>
  <div class="container">
    <Header/>
    <ToDoBox :todos="todos"/>
  </div>
</template>

<script>

import Header from "./components/Header.vue"
import ToDoBox from "./components/todo-box.vue"

export default {
  components:{
    Header,
    ToDoBox,
  },
  data: function(){
    return {
      todos: [{
        title: 'Ubiti se',
        text: 'Ubij se',
        createdAt: '25.09.2021',
        _id: 1,
        important: false
      }],
    }
  }
}
</script>

<style>
  .container{
    height: 100%;
    width: 100%;
    background-color: cornsilk;
  }
</style>

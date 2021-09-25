<template>
    <div class="to-do-box">
        <CreateNewToDo/>
        <ToDoList :todos="todos"/>
    </div>    
</template>

<script>
import CreateNewToDo from "./CreateToDo.vue"
import ToDoList from "./ToDoList.vue"

export default {
    name: 'ToDoBox',
    props:{
        todos: Array,
    },
    components:{
        CreateNewToDo,
        ToDoList,
    }
}
</script>

<style scoped>
    .to-do-box{
        display: flex;
        flex-direction: column;
        width: 50%;
        height: 80%;
        margin: auto;
        margin-top: 2rem;
        border: 2px solid black;
        background-color: #fff;
    }
</style>
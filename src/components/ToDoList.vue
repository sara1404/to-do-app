<template>
    <div class="to-do-list">
        <ToDoItem  :key="todo._id" v-for="todo in todos" :todo="todo"/>
    </div>
</template>

<script>
import ToDoItem from "./ToDoItem.vue"
export default {
    name: 'ToDoList',
    props:{
        todos: Array,
    },
    components:{
        ToDoItem,
    }
}
</script>

<style scoped>
    
</style>
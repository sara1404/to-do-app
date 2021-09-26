<template>
    <div class="to-do-list">
        <ToDoItem  :key="todo._id" v-for="todo in todos" :todo="todo" @removeToDo="$emit('removeToDo', todo._id)"/>
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
    },
    emits:[
        'removeToDo',
    ]
}
</script>

<style scoped>
    .to-do-list{
        overflow-y: scroll;
        border-radius: 10px;
        font-family: 'Urbanist', sans-serif;
    }
    .to-do-list::-webkit-scrollbar {
        width: 13px;
        height: 8px;
        background-color: transparent; /* or add it to the track */
        transition: all 2s;
    }   

    .to-do-list::-webkit-scrollbar-thumb {
        background: rgba(227, 225, 225, 1);
        border-radius: 12px;
    }

</style>
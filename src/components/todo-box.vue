<template>
    <div class="to-do-box">
        <CreateNewToDo @toggle="toggle" :toggle="buttonToggle"/>
        <ToDoForm v-show="buttonToggle" @createToDo="createToDo"/>
        <ToDoList :todos="todos" @removeToDo="removeToDo"/>
    </div>    
</template>

<script>
import CreateNewToDo from "./CreateToDo.vue"
import ToDoList from "./ToDoList.vue"
import ToDoForm from "./ToDoForm.vue"

export default {
    name: 'ToDoBox',
    props:{
        todos: Array,
    },
    components:{
        CreateNewToDo,
        ToDoList,
        ToDoForm,
    },   
    data: function(){
        return {
            buttonToggle: false
        }
    },
    methods: {
        toggle: function() {
            this.buttonToggle = !this.buttonToggle;
        },
        createToDo: function(obj) {
            this.$emit('createdToDo', obj);
            this.toggle();
        },
        removeToDo: function(id){
            this.$emit('removeToDo', id);
        }
    },
    emits: ['createdToDo']
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
        border: 1px solid rgba(227, 225, 225, 1);
        border-radius: 10px;
        background-color: #fff;
    }
</style>
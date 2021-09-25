<template>
    <div class="create-new-to-do">
        <CreateNewToDoButton/>
    </div>  
</template>

<script>
import CreateNewToDoButton from "./CreateToDoButton.vue"
export default {
    name: 'CreateNewToDo',
    components:{
        CreateNewToDoButton,
    }
    
}
</script>

<style scoped>
    .create-new-to-do{
        display: flex;
        justify-content: flex-end;
        max-height: 10%;
        padding: 1rem;
        border-bottom: 2px solid black;
    }
</style>
<template>
    <div class="create-new-to-do">
        <CreateNewToDoButton @click="$emit('toggle')" :toggle="toggle"/>
        
    </div>  
</template>

<script>
import CreateNewToDoButton from "./CreateToDoButton.vue"
export default {
    name: 'CreateNewToDo',
    components:{
        CreateNewToDoButton,
    },
    props:{
        toggle: Boolean,
    },
    emits: ['toggle']

    
}
</script>

<style scoped>
    .create-new-to-do{
        display: flex;
        justify-content: flex-end;
        max-height: 10%;
        padding: 1rem 2rem;
        border-bottom: 2px solid rgba(227, 225, 225, 1);
    }
</style>
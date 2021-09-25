<template>
    <div class="to-do-item">
        <div class="to-do-content">
            <label class="todo-title">{{todo.title}}</label>
            <label class="todo-created-at">{{todo.createdAt}}</label>
        </div>
        <ion-icon name="trash-outline"></ion-icon>
    </div>
</template>

<script>

export default {
    name: 'ToDoItem',
    props:{
        todo: Object,
    }
}
</script>

<style scoped>
    .to-do-item{
        display: flex;
        padding: .5rem;
        background: #ccc4af;
        box-shadow: 1px 1px 4px gray;
    }
    .to-do-content{
        display: flex;
        flex-direction: column;
        flex-grow: 9;
        justify-content: space-around;
        height: 3rem;
        padding: .5rem 1.5rem;
        
        
        font-weight: bold;
    }
    ion-icon{
        display: flex;
        flex-grow: 1;
        align-self: center;
        height: 1.5rem;
        width: 1.5rem;
        color: red;
    }
</style>
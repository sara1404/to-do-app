<template>
    <div class="to-do-item">
        <div class="to-do-item-wrapper" :style="[todo.important ? 'border-left: 3px solid green;' : '']">
            <div class="to-do-content">
                <label class="to-do-title">{{todo.title}}</label>
                <label class="to-do-created-at">{{todo.createdAt}}</label>
            </div>
            <ion-icon name="trash-outline" @click="$emit('removeToDo', todo._id)"></ion-icon>
        </div>  
    </div>
</template>

<script>

export default {
    name: 'ToDoItem',
    props:{
        todo: Object,
    },
    emits:[
        'removeToDo',
    ],
    
}
</script>

<style scoped>
    .to-do-item{
        display: flex;
        padding: .5rem;
        background: #fff;
        box-shadow: 0px 1px 4px gray;
    }
    .to-do-item-wrapper{
        display: flex;
        flex-grow: 1;
        margin: .5rem;
        background: rgba(227, 225, 225, .5);
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
    .to-do-created-at{
        font-size: 0.7rem;
    }
    ion-icon{
        display: flex;
        flex-grow: 1;
        align-self: center;
        height: 1.5rem;
        width: 1.5rem;
        color: red;
        cursor: pointer;
    }
</style>
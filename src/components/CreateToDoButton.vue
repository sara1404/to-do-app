<template>
    <button :style="[toggle ? 'background-color: red;' : 'background-color: #308013;']">{{toggle ? 'Close' : 'Create'}}</button>
</template>

<script>
export default {
    name: 'CreateNewToDoButton',
    props:{
        toggle: Boolean,
    }
}

</script>

<style scoped>
    button{
        width: 7rem;
        min-width: 7rem;
        height: 90%;
        min-height: 2rem;
        background: #308016;
        color: #fff;
        font-weight: bold;
        font-size: 1rem;
        border-radius: .3rem;
        cursor: pointer;
        border: none;
    }
</style>
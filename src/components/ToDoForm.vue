<template>
    <form class="form">
        <div class="title">
            <label><b>Title</b> </label>
            <input type="text" class="title-input" placeholder="eg. Cleaning"  v-model="title"> 
        </div>
        <div class="text">
            <label><b>Text</b> </label>
            <input type="text" class="text-input" placeholder="eg. Do the cleaning tomorow!"  v-model="text">
        </div>
        <div class="wrapper">
            <div class="importance">
                <label>Important: </label>
                <input type="checkbox" class="importance-checkbox" v-model="important">
            </div>
            <button type="submit" @click="createToDo" class="save-button">Save</button>
        </div>
        

    </form>
</template>

<script>
export default {
    name: "ToDoForm",
    data: function(){
        return {
            title: '',
            text: '',
            important: false
        } 
    },
    methods:{
        createToDo: function(e){

            this.$emit('createToDo',{
                title: this.title,
                text: this.text,
                important: this.important,
            });
            this.title = '';
            this.text = '';
            this.important = false;
            e.preventDefault();
        }
    },
    emits:[
        'createToDo',
    ]
}
</script>

<style scoped>
    .form{
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        height: 10rem;
        border-bottom: 1px solid rgba(227, 225, 225, 1);
        padding-left: 3rem;
    }
    .importance label {
        align-self: center;
    }
    .title, .text{
        display: flex;
        flex-direction: column;
    }
    input[type = 'text']{
        max-width: 12rem;
        outline: none;
        border: 2px solid #ff6208;
        border-radius: .5rem;
        min-height:1.5rem;
        padding-left: 0.3rem;
    }
    input[type = 'text']:focus{
        outline: none;
    }
    .wrapper{
        display: flex;
        justify-content: space-between;
        padding-right: 2rem;
    }
    .importance{
        display: flex;
        align-items: center;
        width: 6rem;
        justify-content: space-between;
        font-weight: bold;
    }
    .save-button{
        height: 2rem;
        width: 4rem;
        background-color: #42ba27;
        color: #fff;
        font-weight: bold;
        border-radius: 5px;
        border: none;
        cursor: pointer;
    }

    input[type="checkbox"] {
        align-self: center;
        vertical-align: middle;
    }
    input[type = "checkbox"]:checked{
        filter: invert(1);
        accent-color: #009df7;
    }
</style>
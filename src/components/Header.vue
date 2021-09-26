<template>
    <header>
        <div class="logo">
            <ion-icon name="checkbox-outline"></ion-icon> 
            <span> To Do App</span>
        </div>
        <div class="login-and-signin">
            <a href="">Login</a>
            <a href="">Sign in</a>
        </div>
    </header>
</template>

<script>
export default {
    name: 'Header',
}
</script>

<style scoped>
    header{
        display: flex;
        justify-content: space-between;
        align-items: center;
        width: 100%;
        height: 10vh;
        padding: 0 2rem;
        background: #ff6208;
        color: #fff;
    }
    .logo{
        display: flex;
        align-items: center;
        font-family: 'Birthstone', cursive;
        font-size: 2.7rem;
    }
    .login-and-signin{
        display: flex;
        justify-content: space-between;
        width: 7rem;
       
    }
    a{
        font-size: 1.1rem;
        color: #fff;
        text-decoration: none;
    }
    a:hover{
        text-decoration: underline;
    }
    ion-icon{
        height: 3rem;
        width: 3rem;
        color: #fff;
        margin-right: .5rem;
    }
</style>
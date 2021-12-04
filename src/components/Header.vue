<template>
    <header>
        <h1>{{title}}</h1>
        <Button text = "ADD" color = "green" textColor = "white"/>
        
    </header>
</template>

<script>
import Button from './Button.vue'
export default {
    name : 'Header',
    props: {
        title : String
    },
    components: {
        Button
        }
}
</script>

<style>
/*Adding bootstrap into Vue*/ 
@import'~bootstrap/dist/css/bootstrap.css';

header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
}
h1 {
    font-size: 5rem;
    color: teal;
    text-align: center;
    margin: 0 auto;
    justify-content: center;
    align-self: center;
}
</style>
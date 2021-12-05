<template>
    <header>
        <h1>{{title}}</h1>
        <Button @toggle-add-task="$emit('toggle-add-task')" :text = "showAddTask ? 'Close' : 'Add'" :color = "showAddTask ? 'grey' : 'green'" textColor = "white"/>
        
    </header>
</template>

<script>
import Button from './Button'
export default {
    name : 'Header',
    props: {
        title : String,
        showAddTask : Boolean
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
<template>
     <!-- <div class="container-fluid"> -->
            <div @dblclick="$emit('toggle-reminder', task.id)" :class="[task.reminder ? 'reminder' : '', 'task']">
                <h3>
                {{ task.text }}
                <i @click ="$emit('delete-task', task.id)" class="fas fa-times red"></i>
                </h3>
                <p>{{task.day}}</p> 
            </div>
        <!-- </div> -->
</template>

<script>
export default {
    name: 'Task',
    props: {
        task : Object
    },
}
</script>



<style scoped>
    .red {
        color: red;
    }
    .task {
        background-color: #f4f4f4;
        margin: .5rem;
        padding: 1rem 2rem;
        cursor: pointer;
    }
    .task.reminder {
        border-left: 5px solid green;
    }
    .task h3 {
        display: flex;
        align-content: center;
        justify-content: space-between;
    }

</style>
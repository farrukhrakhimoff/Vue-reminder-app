<template>
     <div class="container-fluid">
            <div :class="[task.reminder ? 'reminder' : '', 'task']">
                <h3>
                {{ task.text }}
                <i @click="onDelete(task.time)" class="fas fa-times"></i>
                </h3>
                <p>{{task.time}}</p>
            </div>
        </div>
</template>

<script>
export default {
    name: 'Task',
    props: {
        task : Object
    },
    methods: {
        onDelete(time) {
            console.log(time);
        }
    }
}
</script>


<style scoped>
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
    .fa-times {
        color: red;
    }

</style>
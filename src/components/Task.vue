<template>
     <!-- <div class="container-fluid"> -->
            <div :class="[task.reminder ? 'reminder' : '', 'task']">
                <h3>
                {{ task.text }}
                <i v-on:click ="onDelete(task.id)" class="fas fa-times red"></i>
                </h3>
                <p>{{task.time}}</p>
            </div>
        <!-- </div> -->
</template>

<script>
export default {
    name: 'Task',
    props: {
        task : Object
    },
    methods: {
        onDelete(id) {
            this.$emit('delete-task', id)
        }
    }
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
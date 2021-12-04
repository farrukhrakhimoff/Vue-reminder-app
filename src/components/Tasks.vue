<template>
   <div class="container-fluid">
        <div v-bind:key="task.id" v-for="task in tasks">
            <Task :task = "task" />
        </div>
   </div>
</template>

<script>
import Task from './Task'
export default {
 name : 'Tasks',
 props: {
     tasks : Array
 },
 components: {
     Task
 }

}
</script>
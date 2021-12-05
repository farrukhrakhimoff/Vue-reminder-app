<template>
  <div class="container">
    <Header @toggle-add-task="toggleAddTask" title="Reminder" :showAddTask="showAddTask"/>
    <div v-if="showAddTask" >
      <AddTask @add-task="addTask"/>
    </div>
    <Tasks @toggle-reminder="toggleReminder" @delete-task="deleteTask" :tasks = 'tasks' />
  <Button/>
  </div>
</template>

<script>
import Header from './components/Header'
import Tasks from './components/Tasks'
import AddTask from './components/AddTask'

export default {
  name: 'App',
  components: {
    Header,
    Tasks,
    AddTask
  },
  data() {
    return {
      tasks : [],
      showAddTask: false
    }
  },
  methods: {
    toggleAddTask() {
      this.showAddTask = !this.showAddTask;
    },
    addTask(task) {
      this.tasks = [...this.tasks, task];
    },
    deleteTask(id) {
      if(confirm("Are you sure to delete the task?")) {
        this.tasks = this.tasks.filter((task) => task.id !== id)
      }
    },
    toggleReminder(id) {
        this.tasks = this.tasks.map((task) => task.id === id ? {...task, reminder: !task.reminder} : task)
    }
  },
  created() {
    this.tasks = [
      {id:1, text:'Working on soft skills', day:'at 10.00 am Monday', reminder : true},
      {id:2, text:'Teaching English', day:'at 7.00 am Wednesday', reminder : false},
      {id:3, text:'Teaching Javascript', day:'at 9.00 pm Friday', reminder : true}
    ]
  }
}
</script>














<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@200&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: "Poppings", sans-serif;
}
html {
  font-size: 62.5%;
}
.container{
  max-width: 50rem;
  margin: 30px auto;
  min-height: 50rem;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}
</style>

<template>
  <div class="container">
    <Header title="Reminder"/>
  <Button/>
  </div>
</template>

<script>
import Header from './components/Header'

export default {
  name: 'App',
  components: {
    Header
  },
  data() {
    return {
      tasks : []
    }
  },
  created() {
    this.tasks = [
      {id:1, text:'Working on soft skills', day:'01.12.2021', time: 'at 10.00 am', reminder : true},
      {id:2, text:'Teaching English', day:'01.12.2021', time: 'at 7.00 am', reminder : true},
      {id:3, text:'Teaching Javascript', day:'01.12.2021', time: 'at 9.00 pm', reminder : true}
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

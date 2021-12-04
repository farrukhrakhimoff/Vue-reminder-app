<template>
  <div class="container">
    <Header title="Reminder"/>
  <Button/>
  </div>
</template>

<script>
import Header from './components/Header'
import Button from './components/Button'




export default {
  name: 'App',
  components: {
    Header,
    Button
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

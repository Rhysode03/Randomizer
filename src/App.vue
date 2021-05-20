<template>
  <div id="app">
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.6.0/dist/css/bootstrap.min.css" integrity="sha384-B0vP5xmATw1+K9KRQjQERJvTumQW0nPEzvF6L/Z6nronJ3oUOFUFpCjEUQouq2+l" crossorigin="anonymous">
  <div class="container mx-auto">
  <div class="row">
  <div class="col">
    <img alt="Siftd logo" src="./assets/logo.png">
    <img style="background-color: #107C10; width: 300px;" alt="Game Pass or Fail logo" src="./assets/Game_Pass_or_Fail_Logo_White.png">
    <HelloWorld/>
    </div>
    </div>
    </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style src="">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
img{
  width: 250px;
  height: 300px;
}
</style>

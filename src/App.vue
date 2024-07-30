<template>
  <header class="header">
    <img alt="Vue logo" src="./assets/dawg.png">
    <span class = "title"> To-Do List </span>
  </header>
  <HelloWorld msg="Welcome to Your Vue.js App"/>
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

<style>

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000000;
  margin-top: 60px;
  
}

.header {
  margin: 0 25%;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 20px; 
  border: 3em solid #7eb5f3;
  border-radius: 8px 8px 0 0;
  border-bottom: 0;
  background-color: white;
}

.title {
  font-size: 54px; /* Adjust the size as needed */
  font-weight: bold;
}


</style>

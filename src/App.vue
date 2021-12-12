<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Secret-Santa App"/>
  <LogMail/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import LogMail from "./components/LogMail";

export default {
  name: 'App',
  components: {
    LogMail,
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
  color: #2c3e50;
  margin-top: 60px;
}
</style>

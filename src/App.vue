<template>
  <div id="app">
    <img src="./assets/logo.png">
    <Keyboard msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import Keyboard from './components/Keyboard.vue'

export default {
  name: 'app',
  components: {
    Keyboard
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

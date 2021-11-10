<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld/>
    <br/>
    <WeatherTest/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import WeatherTest from './components/Weathertest.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    WeatherTest
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

<template>
  <FirstModule></FirstModule>
</template>

<script>
import FirstModule from './components/FirstModule.vue'

export default {
  name: 'App',
  components: {
    FirstModule
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

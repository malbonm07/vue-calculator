<template>
  <div id="app">
    <AppCalculator msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import AppCalculator from './components/AppCalculator.vue'

export default {
  name: 'app',
  components: {
    AppCalculator
  }
}
</script>

<style lang="scss">
@import './scss/styles';
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  position: relative;
}
</style>

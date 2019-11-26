<template>
  <div id="app">
    <pic/>
  </div>
</template>

<script>
import pic from './components/pic'


export default {
  name: 'App',
  components: {
    pic
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

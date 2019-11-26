<template>
  <div id="app">
    <pic/>
    <btn/>
  </div>
</template>

<script>
import pic from './components/pic'
import btn from './components/btn'

export default {
  name: 'App',
  components: {
    pic,
    btn
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

<template>
  <div id="app">
    <HeaderComp/>
    <HelloWorld/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import HeaderComp from './components/Header'

export default {
  name: 'app',
  components: {
    HelloWorld,
    HeaderComp
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
}
</style>

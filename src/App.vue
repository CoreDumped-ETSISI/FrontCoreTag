<template>
  <div id="app">
    <HeaderComp/>
    <div v-if="page == 'NewPlayer'">
      <!--New component will be displayed from here-->
      <NewPlayer/>
    </div>
    <div v-if="page == 'IntroCenter'">
    <IntroCenter/>
    </div>
    <div v-if="page == 'Match'">
      <Match/>
    </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import HeaderComp from './components/Header'
import IntroCenter from './components/IntroCenter'
import NewPlayer from './components/NewPlayer'
import Match from './components/Match'

export default {
  name: 'app',
  data: function(){
    return {
      page: 'IntroCenter'
    }
  },
  components: {
    HelloWorld,
    HeaderComp,
    IntroCenter,
    NewPlayer,
    Match
  },
  created() {
    this.$on('ChangeView', function (view) {
      this.page = view;
    });
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

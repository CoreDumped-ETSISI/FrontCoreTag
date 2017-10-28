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
    <div v-if="page == 'Player'">
      <Player/>
    </div>
    <div v-if="page == 'MatchSelection'">
      <MatchSelection/>
    </div>
  </div>
</template>

<script>
import HeaderComp from './components/Header'
import IntroCenter from './components/IntroCenter/IntroCenter'
import NewPlayer from './components/NewPlayer/NewPlayer'
import Match from './components/Match/Match'
import Player from './components/Player/Player'
import MatchSelection  from './components/MatchSelection/MatchSelection'

export default {
  name: 'app',
  data: function(){
    return {
      page: 'IntroCenter'
    }
  },
  components: {
    HeaderComp,
    IntroCenter,
    NewPlayer,
    Match,
    Player,
    MatchSelection
  },
  created() {
    this.$on('ChangeView', function (view) {
      this.page = view;
    });
  }
}
</script>

<style>
	@import url('https://fonts.googleapis.com/css?family=Merriweather|Roboto');	
		
	#app {
		font-family: 'Roboto', Helvetica, Arial, sans-serif;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
		text-align: center;
		color: #ccc;
		background-color: #071930;
	}
	
	body{
		font-family: 'Roboto', Helvetica, Arial, sans-serif;
		font-size: 14pt;
		background-color: #071930;
	}
	
	.btn-red{
		background-color: #851934;
		color: white;
		text-shadow: 2px 2px 2px #071930;
	}
	.btn-blue{
		background-color: #03A694;
		color: white;
		text-shadow: 2px 2px 2px #071930;
	}
	
	.btn-large{
		color: white;
		text-shadow: 2px 2px 2px #071930;
		font-family: 'Merriweather';
		font-size: 12pt;
	}
</style>

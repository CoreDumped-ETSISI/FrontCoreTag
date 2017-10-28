<template>
<div class="nicknameInput">
    <div class ="input-field col s6">
          <div class="row">
    <form class="col s12">
      <div class="row">
        <div class="col s12">
          Enter desired nickname. Make sure you pick a cool one!:
          <div class="input-field inline">
            <input id="nickname" type="text" class="validate">
            <label>Nickname</label>
          </div>
        </div>
      </div>
    </form>
  </div>
        <a class="waves-effect waves-light btn-large" v-on:click="createPlayer">Create!</a>
    </div>        
</div>
</template>

<script>
import axios from 'axios';

export default {

    name: 'NewPlayer',
        methods: {
            createPlayer (event) {
                console.log('New player sign up requested;')
                var nick = document.getElementById("nickname").value
                //HTTP request must be done here. And below line must be placed only when 
                //request success (responseCode = 200).
                axios.post('http://192.168.0.25:3000/api/createUser', 
                    {"nickname": "" + nick})
                    .then(response => {
                    if(response.data == 200) {
                        this.$parent.$emit('ChangeView', 'IntroCenter');
                    }
                }).catch(e => {
                    console.log(e)
                });
}
        }
}
</script>

<style scoped>
	input:not([type]), input[type="text"]:not(.browser-default), input[type="password"]:not(.browser-default), input[type="email"]:not(.browser-default), input[type="url"]:not(.browser-default), input[type="time"]:not(.browser-default), input[type="date"]:not(.browser-default), input[type="datetime"]:not(.browser-default), input[type="datetime-local"]:not(.browser-default), input[type="tel"]:not(.browser-default), input[type="number"]:not(.browser-default), input[type="search"]:not(.browser-default), textarea.materialize-textarea {
		font-size: 14pt;
		}
	.input-field.inline{
		vertical-align: baseline;
	}
	
	.input-field.inline input, .input-field.inline .select-dropdown {
	margin-bottom: 1rem;
	margin-left: 0.5rem;
}
	
		
</style>
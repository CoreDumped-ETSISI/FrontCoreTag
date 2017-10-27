<template>
<div class="nicknameInput">
    <div class ="input-field col s6">
          <div class="row">
    <form class="col s12">
      <div class="row">
        <div class="col s12">
          Enter desired nickname. Coolest ones rocks!:
          <div class="input-field inline">
            <input id="email" type="email" class="validate">
            <label for="email" data-error="wrong" data-success="right">Nickname</label>
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
export default {
    name: 'NewPlayer',
        methods: {
            createPlayer (event) {
                console.log('New player sign up requested;')
                //HTTP request must be done here. And below line must be placed only when 
                //request success (responseCode = 200).
                /*
                this.$http.get('ROUTE', function(data, status, response) {
                this.users = data;
            }).error(function (data, status, request) {
                // handle error
            }); */
                this.$parent.$emit('ChangeView', 'IntroCenter');
            }
        }
}
</script>
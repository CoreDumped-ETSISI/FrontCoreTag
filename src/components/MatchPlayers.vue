<<template>
    <div class="teamMatchup">
      <p>Choose your nickname: </p>

      <div class="row">
        <div class="col s12">
          <div class="row">
            <div class="input-field col s12">
              <input type="text" id="autocomplete-input" class="autocomplete">
              <label for="autocomplete-input">Type your nickname!</label>
            </div>
            <a class="waves-effect waves-light btn-large" v-on:click="joinMatch()">Join!</a>
          </div>
        </div>
        <div class="row">
          <div class="col s6 blueTeamTitle">
              <span class="flow-text">Blue Team</span>
              <td id="blueTeamTable">
              </td>
          </div>
          <div class="col s6 redTeamTitle">
              <span class="flow-text">Red Team</span>
              <td id="redTeamTable">
              </td>
          </div>
    </div>
      </div>
    </div>

</template>

<script>
export default {
  name:'Players',
  data: function(){
    return {
      playerAmount: 0
    }
  },
  created: function () {
    $(document).ready(function(){
  $('input.autocomplete').autocomplete({
    data: {
      //Replace data with requested nicknames from database.
      "Apple": null,
      "Microsoft": null,
      "Google": 'https://placehold.it/250x250'
    }
  });
    });    
  },
  methods: {
    joinMatch (event){
      //PLEASE DELETE ALL HTML INJECTION CODE!!!
      var newPlayer = document.getElementById("autocomplete-input").value
      console.log(newPlayer.toString())
      if(this.playerAmount < 2){
        $('#blueTeamTable').append('<p id="hida">NewPlayer</p>');
      } else if(this.playerAmount >=2 && this.playerAmount < 4){
        $('#redTeamTable').append('<p id="hidb">NewPlayer</p>');
      }
      this.playerAmount++;
      //Add player to a team (Blue or Red).
      console.log("Adding player to a team.")
    }
  }
}
</script>
<style scoped>
  .blueTeamTitle{
    background-color: #03A694;
	border-radius: 5pt 0pt 0pt 5pt;
    color: #071930;
	font-family: 'Merriweather';
	font-size: 12pt;
	padding: 10px;
  }
  .redTeamTitle{
    background-color: #F24738;
	border-radius: 0pt 5pt 5pt 0pt;
	padding: 10px;
	font-family: 'Merriweather';
    color: #071930; 
	font-size: 12pt;
  }
  .flow-text{
	font-size:24pt;
	padding: 0px;
	}
</style>


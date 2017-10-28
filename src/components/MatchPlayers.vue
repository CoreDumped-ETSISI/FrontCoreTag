<template>
    <div class="teamMatchup">
        <p>Choose your nickname: </p>

        <div class="row">
            <div class="col s12">
                <div class="row">
                    <div class="input-field col s6">
                        <input type="text" id="autocomplete-input" class="autocomplete">
                        <label for="autocomplete-input">Type your nickname!</label>
                    </div>
                    <div class="input-field col s6">
                        <input type="text" id="weapon-id" class="weapon-id">
                        <label>Type your weapon!</label>
                    </div>
                    <a class="waves-effect waves-light btn-large" v-on:click="joinMatch()">Join!</a>
                </div>
            </div>
            <div class="row">
                <div class="col s6 blueTeamTitle">
                    <span class="flow-text">Blue Team</span>
                    <td id="blueTeamTable">
                        <span class="blue-player player-element" v-for="player  in blueTeam">{{player[0]}}</span>
                    </td>
                </div>
                <div class="col s6 redTeamTitle">
                    <span class="flow-text">Red Team</span>
                    <td id="redTeamTable">
                        <span class="red-player player-element" v-for="player in redTeam">{{player[0]}}</span>
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
            playerAmount: 0,
            blueTeam: [],
            redTeam: []
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
            var newPlayer = document.getElementById("autocomplete-input").value
            var newWeapon = document.getElementById("weapon-id").value
            document.getElementById("autocomplete-input").value = ""
            document.getElementById("weapon-id").value = ""
            if(this.playerAmount < 2){
                this.blueTeam.push([newPlayer.toString(), newWeapon.toString()]);
                this.$parent.$emit('blueTeam', this.blueTeam);
            } else if(this.playerAmount >=2 && this.playerAmount < 4){
                this.redTeam.push([newPlayer.toString(), newWeapon.toString()]);
                this.$parent.$emit('redTeam', this.redTeam);
            }
            this.playerAmount++;
            //Add player to a team (Blue or Red).
        }
    }
}
</script>

<style scoped>
.blueTeamTitle{
    background-color: #03A694;
    border-radius: 5pt 0pt 0pt 5pt;
    color: white;
	text-shadow: 2px 2px 2px #071930;
    font-family: 'Merriweather';
    font-size: 12pt;
    padding: 10px;
}
.redTeamTitle{
    background-color: #F24738;
    border-radius: 0pt 5pt 5pt 0pt;
    padding: 10px;
    font-family: 'Merriweather';
    color: white;
	text-shadow: 2px 2px 2px #071930;
    font-size: 12pt;
}

.player-element{
	color: #071930;
	font-size: 16pt;
	text-shadow: none;
	background-repeat: no-repeat;
	padding: 0	0 7px 35px;	/* width of the image plus a little extra padding */
	display: block;  /* may not need this, but I've found I do */
}
.blue-player{
	background-image: url('../assets/pistol-red.png');
}
.red-player{
	background-image: url('../assets/pistol-blue.png');
}


.flow-text{
    font-size:24pt;
    padding: 0px;
}
</style>


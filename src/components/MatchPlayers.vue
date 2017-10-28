<template>
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
            playerAmount: 0,
            blueTeam: [
                null
            ],
            redTeam: [
                null
            ]
            
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
<style>
.blueTeamTitle{
    background-color: blue;
    color: white;
}
.redTeamTitle{
    background-color: red;
    color: black;
}
</style>


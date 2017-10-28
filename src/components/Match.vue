<template>
    <div class="row main">
        <br>
        <form class="col s6 offset-s3">
            <div class="row">
                <!--<Type/><br>-->
                <Duration/><br>
                <Players/><br>
                <Lifes/>
                <br>
                <a class="btn waves-effect waves-light btn-large col s8" v-on:click="createMatch">
                    Submit
                </a>
            </div>
        </form>
    </div>
</template>

<script>
import Type from './MatchType'
import Duration from './MatchDuration'
import Players from './MatchPlayers'
import Lifes from './MatchLifes'

export default {
    name: 'Match',
    data: function () {
        return{
            duration: 'infinite',
            durationTime: '0',
            life: 0,
            blueTeam: null,
            redTeam: null
        }
    },
    components: {
        Type,
        Duration,
        Players,
        Lifes
    },
    methods:{
        createMatch (){
            var time;
            if(this.duration == 'infinite')
                time=-1;
            else{
                time=this.durationTime;
            }
            var jsonToReturn = '{"time":"'+time+'","teams": [{'+
                this.blueTeam+'},{'+this.redTeam+'}],"life":"'+this.life+'"}';
            console.log(jsonToReturn);

            $.post("http://192.168.0.25:3000/api/createMatch", //Required URL of the page on server
                { // Data Sending With Request To Server
                    "match":jsonToReturn,
                },
                function(response,status){
                    console.log("Match Creatred");
                    this.$parent.$emit('ChangeView', 'Player');
                    //alert("*-Received Data-*\n\nResponse : " + response+"\n\nStatus : " + status);
                });
        }

    },
    created() {
        this.$on('duration', function (msg) {
            this.duration = msg;
        });
        this.$on('durationTime', function(msg) {
            this.durationTime = msg;
        });
        this.$on('life', function(msg){
            this.life = msg;
        });
        this.$on('redTeam', function(msg){
            if(msg.length == 1)
                this.redTeam = '"redTeam":[{"gun":"'+msg[0][0]+'","idUser":"'+msg[0][1]+'"}]';
            else
                this.redTeam = '"redTeam":[' +
                    '{"gun":"'+msg[0][0]+'","idUser":"'+msg[0][1]+'"},'+
                    '{"gun":"'+msg[1][0]+'","idUser":"'+msg[1][1]+'"}'+ 
                    ']';
        });
        this.$on('blueTeam', function(msg){
            if(msg.length == 1)
                this.blueTeam = '"blueTeam":[{"gun":"'+msg[0][0]+'","idUser":"'+msg[0][1]+'"}]';
            else
                this.blueTeam = '"blueTeam":[' +
                    '{"gun":"'+msg[0][0]+'","idUser":"'+msg[0][1]+'"},'+
                    '{"gun":"'+msg[1][0]+'","idUser":"'+msg[1][1]+'"}'+ 
                    ']';
        });
    }
}
</script>

<style>

</style>

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
            life: 0
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
            console.log(this.duration);
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
    }
}
</script>

<style>

</style>

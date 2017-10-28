<template>

<div class="buttonContainer row">
    <div class="col s12">
    <a class="waves-effect waves-light btn-large" v-on:click="toNewPlayer">New Player</a>
     <a class="waves-effect waves-light btn-large" v-on:click="toMatch">Match!</a>
    </div>
    <div class="col s12">
     <a class="waves-effect waves-light btn-large" v-on:click="toPlayer">Player!</a>
     <a class="waves-effect waves-light btn-large" v-on:click="toMatchSelection">View!</a>
    </div>
</div>
</template>

<script>
    export default {
        name:'IntroCenter',
        methods: {
            toNewPlayer (event) {
                this.$parent.$emit('ChangeView', 'NewPlayer');
            },
            toMatch (event) {
                this.$parent.$emit('ChangeView', 'Match');
            },
            toPlayer (event) {
                this.$parent.$emit('ChangeView', 'Player');
            },
            toMatchSelection (event) {
                this.$parent.$emit('ChangeView', 'MatchSelection');
            }
        }
    }
</script>

<style scoped>
    .buttonContainer{
        margin-top: 15%;
		background-color: #071930;
    }
	.btn-large{
		padding-left: 20 px;
		background-color: #03A694;
	}
    .col{
        padding: 20px;
    }
</style>

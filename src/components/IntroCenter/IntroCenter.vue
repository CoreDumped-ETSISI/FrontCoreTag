<template>

<div class="buttonContainer row">
    <div class="col s12">
		<a class="waves-effect waves-light btn-large intro-width btn-blue" v-on:click="toNewPlayer">New Player</a>
    </div>
	<div class="col s12">
		<a class="waves-effect waves-light btn-large intro-width btn-blue" v-on:click="toMatch">Match!</a>
    </div>
	<div class="col s12">
		<a class="waves-effect waves-light btn-large intro-width btn-blue" v-on:click="toPlayer">Player!</a>
    </div>
	<div class="col s12">
		<a class="waves-effect waves-light btn-large intro-width btn-blue" v-on:click="toMatchSelection">View!</a>
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
        margin-top: 0;
		background-color: #071930;
    }
	.btn-large{
		margin: 10pt 0 0 0;
		font-family: 'Merriweather';
		font-size: 18pt;
	}
	.intro-width{
		max-width:500px;
		width: 75%; 
	}
</style>

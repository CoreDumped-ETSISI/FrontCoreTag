<template>

<div class="buttonContainer">
    <a class="waves-effect waves-light btn-large" v-on:click="toNewPlayer">New Player</a>
     <a class="waves-effect waves-light btn-large" v-on:click="toMatch">Match!</a>
     <a class="waves-effect waves-light btn-large" v-on:click="toPlayer">Player!</a>
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
            }
        }
    }
</script>

<style scoped>
    .buttonContainer{
        margin-top: 20%;
		background-color: #071930;
    }
	.btn-large{
		background-color: #03A694;
	}
</style>

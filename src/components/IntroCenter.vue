<template>

<div class="buttonContainer">
    <a class="waves-effect waves-light btn-large" v-on:click="toNewPlayer">New Player</a>
    <a class="waves-effect waves-light btn-large" v-on:click="toMatch">Match!</a>
</div>
</template>

<script>
    export default {
        name:'IntroCenter',
        methods: {
            toNewPlayer (event) {
                console.log('New player requested;')
                this.$parent.$emit('ChangeView', 'NewPlayer');
            },
            toMatch (event) {
                console.log('New player requested;')
                this.$parent.$emit('ChangeView', 'Match');
            }
        }
    }
</script>

<style scoped>
    .buttonContainer{
        margin-top: 30%;
    }
</style>
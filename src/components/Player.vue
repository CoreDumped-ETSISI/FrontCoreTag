<template>
    <div class="row">
        <div class="col s6">
    	<Lifes/></br>
        </div>
        <div class="col s8">
    	<Chart/></br>
        </div>
    </div>
</template>

<script>
import Lifes from './PlayerLifes'
import Chart from './LobbyChart'

export default {
    name: 'Player',
    components: {
	Lifes,
	Chart
    },
}
</script>

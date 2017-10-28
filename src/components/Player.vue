<template>
    <div>
    	<Lifes/><br>
    	<Chart/><br>
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

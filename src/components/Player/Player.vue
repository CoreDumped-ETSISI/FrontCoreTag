<template>
    <div>
    	<Lifes/><br>
    	<Chart/><br>
    </div>
</template>

<script>
import Lifes from './Lifes/PlayerLifes'
import Chart from './Chart/LobbyChart'

export default {
    name: 'Player',
    components: {
	Lifes,
	Chart
    },
}
</script>

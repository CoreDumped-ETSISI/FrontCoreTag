<template>
	<div class="row">
		<div class="col s6 right-align" v-for="life in lifes">
			x{{ life.message }}
		</div>
		<div class="col s6 left-align">
			<img src="../images/heart.png" style="max-width: 2em">
		</div>
      	</div>
</template>

<script>
export default {
    name: 'Lifes',
    data: function() {
	return {
		page: 'IntroCenter',
		lifes: [
			{ message: 3 }
		]
	}
    }
}
</script>

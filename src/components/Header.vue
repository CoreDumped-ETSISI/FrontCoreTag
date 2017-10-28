<template>
<nav>
  <div class="nav-wrapper pink lighten-3">
    <span class="brand-logo">Laser Tag</span>
  </div>
</nav>
</template>

<script>
export default {
    name: 'HeaderComp'
}
</script>

<style scoped>
	.pink.lighten-3 {
		background-color: #023852 !important;
	}
	.brand-logo{
		background-image: url('../assets/logo2.png');
		background-repeat: no-repeat;
		background-size: contain;
		background-position: center;
		text-indent: -999999em;
		display: inline-block;
		width: 100%;
		height: 100%;
	}
</style>

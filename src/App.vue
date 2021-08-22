<template>
	<nav-bar></nav-bar>

	<the-product></the-product>
</template>

<script>
	import NavBar from "./components/NavBar.vue";
	import TheProduct from "./components/TheProduct.vue";

	export default {
		components: {
			NavBar,
			TheProduct
		}
	};
</script>

<style>
	#app {
		font-family: Avenir, Helvetica, Arial, sans-serif;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
		text-align: center;
		color: #2c3e50;
		margin-top: 60px;
	}
</style>

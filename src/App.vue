<template>
	<LoginPage />
</template>

<script>
import LoginPage from './pages/LoginPage.vue';

export default {
	name: 'App',
	components: {
		LoginPage
	}
}
</script>

<style>
@import '~@/assets/scss/main.scss';

#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin: 0;
	padding: 0;
}
</style>

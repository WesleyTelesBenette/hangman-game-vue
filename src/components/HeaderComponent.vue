<template>
	<header class="anim-slide-down-delay">
		<nav class="nav-container">
			<a class="nav-logo">Hangman Game</a>
			<a v-if='isLogin' class="nav-profile click">
				<img class="nav-profile-image" src="~@/assets/profile.svg"/>
			</a>
			<a v-else class="click">Entrar / Criar Conta</a>
		</nav>
	</header>
</template>

<script>
export default {
	name: "HeaderComponent",
	computed: {
		isLogin() { //For now
			return true;
		}
	}
}
</script>

<style>
header {
	.nav-container {
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 0px 50px;
		user-select: none;

		background-color: var(--back-normal);
		width: 100%;
		height: 60px;

		.nav-logo {
			display: flex;
			justify-content: center;
			align-items: center;

			height: 100%;

			font-size: 2.8em;
			font-family: "Nunito Sans";
			font-weight: 100;
			font-variant-caps: all-petite-caps;
		}

		.nav-profile {
			padding: 10px;

			background-color: var(--back-light);
			height: 100%;

			.nav-profile-image {
				height: 40px;
			}
		}
	}
}
</style>
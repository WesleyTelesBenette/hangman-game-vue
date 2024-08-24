<template>
	<div class="menu-page">
		<div class="menu-container">
			<header class="anim-slide-down-delay">
				<nav class="nav-container">
					<a class="nav-logo">Hangman Game</a>
					<a class="nav-profile">Conta</a>
				</nav>
			</header>
			<main>

			</main>
		</div>
		<FooterComponent class="anim-slide-up-delay"/>
	</div>
</template>

<script>
import FooterComponent from '@/components/FooterComponent.vue';

export default {
	name: 'MenuPage',
	components: {
		FooterComponent
	}
}
</script>

<style>
.menu-page {
	display: flex;
	flex-direction: column;
	justify-content: space-between;
	
	background-color: var(--back-dark);
	min-width: 100%;
	max-width: 100%;
	min-height: 100vh;

	.menu-container {
		width: 100%;

		header {
			.nav-container {
				display: flex;
				justify-content: space-between;
				align-items: center;
				padding: 0px 50px;
	
				background-color: var(--back-normal);
				width: 100%;
				height: 60px;

				.nav-logo {
					display: flex;
					justify-content: center;
					align-items: center;

					height: 100%;

					font-size: 2em;
				}
			}
		}

		main {

		}
	}
}
</style>
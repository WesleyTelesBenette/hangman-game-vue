<template>
	<div class="menu-page">
		<div class="menu-container">
			<HeaderComponent/>
			<main>
			</main>
		</div>
		<FooterComponent class="anim-slide-up-delay"/>
	</div>
</template>

<script>
import FooterComponent from '@/components/FooterComponent.vue';
import HeaderComponent from '@/components/HeaderComponent.vue';

export default {
	name: 'MenuPage',
	components: {
		FooterComponent, HeaderComponent
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

		main {

		}
	}
}
</style>
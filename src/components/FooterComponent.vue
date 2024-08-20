<template>
	<footer class="footer">by Wesley T. Benette</footer>
</template>

<script>
export default {
	name: 'FooterComponent'
}
</script>

<style>
.footer {
	position: fixed;
	display: flex;
	justify-content: center;
	align-items: center;
	bottom: 0;


	background-color: var(--back-normal);
	min-width: 100vw;
	max-width: 100vw;
	height: 35px;
}
</style>
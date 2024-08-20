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
	display: flex;
	justify-content: center;
	align-items: center;
	bottom: 0;

	background-color: var(--back-normal);
	min-width: 100%;
	max-width: 100%;
	height: 35px;
}
</style>
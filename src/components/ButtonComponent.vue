<template>
	<input class="button click-soft" :type="type" :value="text"/>
</template>

<script>
export default {
	name: 'ButtonComponent',
	props: {
		type: {
			type: String,
			default: 'button',
			validator: (value) => {
				return ['submit', 'button'].includes(value);
			}
		},
		text: {
			type: String,
			default: 'click'
		}
	}
};
</script>

<style>
.button {
	width: 100%;
	height: 35px;
	background-color: var(--back-marked);
	border: none;
	border-radius: 10px;

	color: var(--text-normal);

	transition: background-color .1s, color .3s, font-weight .2s;

	&:active {
		opacity: 1;
		background-color: transparent;
		border: 2px solid var(--back-marked);

		color: var(--text-marked);
		font-weight: 800;
	}
}
</style>

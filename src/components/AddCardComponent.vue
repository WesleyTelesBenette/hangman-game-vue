<template>
	<div @click='clickOnAdd' class='add-container click-color-noback anim-size-pop-delay'>
		+
	</div>
</template>

<script>
export default {
	name: 'AddCardComponent',
	methods: {
		clickOnAdd() {
			this.$emit('click-add', this.content);
		}
	}
}
</script>

<style>
.add-container {
	display: inline-block;
	user-select: none;
	padding: 20px 15px;

	width: 100%;
	border: 2px dashed var(--back-light);
	border-radius: 8px;

	font-size: 1.2em;
	white-space: nowrap;
	overflow: hidden;
	text-overflow: ellipsis;
}
</style>
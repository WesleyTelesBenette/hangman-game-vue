<template>
	<div @click='clickOnCard' class='card-container click anim-size-pop-delay'>
		{{ content }}
	</div>
</template>

<script>
export default {
	name: 'CardComponent',
	props: {
		content: {
			type: String,
			default: ''
		}
	},
	methods: {
		clickOnCard() {
			this.$emit('click-card', this.content);
		}
	}
}
</script>

<style>
.card-container {
	display: inline-block;
	user-select: none;
	padding: 20px 15px;

	width: 100%;
	background-color: var(--back-light);
	border-radius: 8px;

	font-size: 1.2em;
	white-space: nowrap;
	overflow: hidden;
	text-overflow: ellipsis;
}
</style>
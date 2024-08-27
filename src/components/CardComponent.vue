<template>
	<div class='card-container anim-size-pop-delay'>
		<div class='card-element'>
			{{ content }}
		</div>
		<div class='card-buttons'>
			<a @click='buttonsAction("play")' class='click-hard'><img class='card-button-image' src='~@/assets/play.svg'/></a>
			<a @click='buttonsAction("copy")' class='click-hard'><img class='card-button-image' src='~@/assets/copy.svg'/></a>
			<a @click='buttonsAction("edit")' class='click-hard'><img class='card-button-image' src='~@/assets/edit.svg'/></a>
			<a @click='buttonsAction("delete")' class='click-hard'><img class='card-button-image' src='~@/assets/delete.svg'/></a>
		</div>
	</div>
</template>

<script>
export default {
	name: 'CardComponent',
	props: {
		idCard: {
			type: Number
		},
		content: {
			type: String,
			default: ''
		}
	},
	methods: {
		buttonsAction(action) {
			const validAction = ['play', 'copy', 'edit', 'delete'].includes(action);

			if (validAction) {
				this.$emit('buttons-action', this.idCard, action);
				return;
			}
			throw Error('Origin: CardComponent->buttonsAction()');
		}
	}
}
</script>

<style>
.card-container {
	display: flex;
	flex-direction: column;
	justify-content: space-between;
	user-select: none;
	overflow: hidden;
	padding: 15px 15px;

	width: 100%;
	height: 120px;
	border: 2px solid var(--back-light);
	border-radius: 8px;

	.card-element {
		padding: 10px;

		background-color: var(--back-normal);
		border-radius: 10px;

		white-space: nowrap;
		overflow: hidden;
		text-overflow: ellipsis;
	}

	.card-buttons {
		display: flex;
		flex-direction: row;
		justify-content: space-evenly;
		align-items: center;

		max-width: 100%;
		height: 20px;

		.card-button-image {
			opacity: .9;
			max-height: 30px;
		}
	}
}

</style>
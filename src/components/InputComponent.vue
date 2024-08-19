<template>
	<div class='input-container'>
		<label v-if='label !== ""' :id="idInput" class="input-label"> {{ label }} </label>
		<div class="input-field-container">
			<input required :id="idInput" class='input-field' :placeholder='placeHolder' :type='getType' v-model='valueInput' />
			<a v-if='this.type === "password"' @click='toogleEye()' class='input-eye click' type='button'>
				<img v-show='eye' class="input-eye-image" src='~@/assets/eye.svg'/>
				<img v-show='!eye' class="input-eye-image eye-off" src='~@/assets/eye-off.svg'/>
			</a>
		</div>
	</div>
</template>

<script>
export default {
	name: 'InputComponent',
	props: {
		idInput: {
			type: String,
			default: ''
		},
		label: {
			type: String,
			default: ''
		},
		placeHolder: {
			type: String,
			default: ''
		},
		type: {
			type: String,
			default: 'text',
			validator: (value) => {
				return ['text', 'password', 'email'].includes(value);
			}
		}
	},
	data() {
		return {
			eye: false
		}
	},
	methods: {
		toogleEye() {
			this.eye = !this.eye;
		}
	},
	computed: {
		getType() {
			if ((this.type === 'text') || (this.type === 'email'))
				return this.type;

			return (this.eye)
				? 'text'
				: 'password';
		},
	},
	watch: {
		valueInput(newValue) {
			this.$emit('update:value', newValue);
		}
	}
};
</script>

<style>
.input-label {
	display: flex;
	padding-left: 10px;

	width: 100%;
}
.input-container {
	display: flex;
	flex-direction: column;
	width: 100%;
	gap: 3px;

	.input-field-container {
		display: flex;
		justify-content: space-between;
		align-items: center;
		max-width: 100%;
		min-width: 100%;
		height: 3em;

		.input-field {
			box-sizing: border-box;
			padding: 0px 20px;
			padding-right: 40px;
	
			min-width: 100%;
			min-height: 100%;
			max-height: 100%;
			background-color: transparent;
			border: 2px solid var(--border-normal);
			border-radius: 20px;
	
			color: var(--text-normal);
	
			&:focus {
				outline: none;
				box-shadow: 0 0 10px var(--border-shadow);
				border-color: var(--border-marked);
			}
	
			transition: box-shadow .4s, border-color .3s;
		}
	}

	.input-eye {
		display: flex;
		justify-content: center;
		align-items: center;

		transform: translateX(-50px);
		height: 100%;

		.input-eye-image {
			margin-left: 10px;
			width: 25px;

			&.eye-off {
				opacity: .5;
			}
		}
	}
}
</style>

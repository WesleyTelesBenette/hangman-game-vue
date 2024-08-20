<template>
	<div class="login-page">
		<div class='login-container'>
			<div class='logo-container anim-size-pop'>
				<img class='logo-image' src='~@/assets/logo.png'/>
				<h2 class='logo-subtitle'>Venha 3nf0rc@r suas ideias com a gente!</h2>
			</div>
			<form class='login-inputs'>
				<InputComponent idInput="email" label="Email" class="anim-size-pop" type='email' v-model='email' placeHolder='Digite seu e-mail...'/>
				<InputComponent idInput="password" label="Senha"  class="anim-size-pop" type='password' v-model='password' placeHolder='Digite a senha...' />
				<div class='login-buttons'>
					<ButtonComponent class="anim-size-pop" @click="loginAccount" type='submit' text='Entrar' />
					<ButtonComponent class="anim-size-pop" @click="createAccount" type='submit' text='Criar Conta'/>
				</div>
			</form>
		</div>
		<FooterComponent class="anim-slide-up"/>
	</div>
</template>

<script>
import InputComponent from '@/components/InputComponent.vue';
import ButtonComponent from '@/components/ButtonComponent.vue';
import FooterComponent from '@/components/FooterComponent.vue';

export default {
	name: 'LoginPage',
	components: { InputComponent, ButtonComponent, FooterComponent },
	data() {
		return {
			email: '',
			password: ''
		};
	},
	methods: {
		createAccount() {

		},
		loginAccount() {

		}
	},
};
</script>

<style>
.login-page {
	box-sizing: border-box;
	display: flex;
	flex-direction: column;
	justify-content: space-between;
	align-items: center;
	gap: 20px;

	background-color: var(--back-dark);
	min-width: 100%;
	max-width: 100%;
	min-height: 100vh;
	max-height: 100%;
	
	.login-container {
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 50px;

		width: 425px;
		max-width: 90%;

		.logo-container {
			display: flex;
			flex-direction: column;
			align-items: center;
			margin-top: 10%;
			gap: 20px;

			width: 100%;
			
			.logo-image {
				user-select: none;
				width: 400px;
				max-width: 90%;
			}

			.logo-subtitle {
				color: var(--text-dark);
				width: 90%;
			}
		}

		.login-inputs {
			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;
			gap: 10px;

			width: 100%;

			.login-buttons {
				display: flex;
				flex-direction: row;
				align-items: center;
				justify-content: space-around;
				margin-top: 20px;

				width: 100%;

				.button {
					width: 45%;
				}

				@media only screen and (max-width: 300px) {
					flex-direction: column;
					gap: 10px;
					.button {
						width: 100%;
					}
				}
			}
		}
	}
}
</style>

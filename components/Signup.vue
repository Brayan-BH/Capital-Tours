<template>
	<div class="container-form">
		<form class="form" id="form" action="/">
			<h1>Registrate</h1>
			<div class="input-control">
				<label for="username">Usuario</label>
				<input id="username" name="username" type="text">
				<div class="error"></div>
			</div>
			<div class="input-control">
				<label for="email">Correo Electronico</label>
				<input id="email" name="email" type="text">
				<div class="error"></div>
			</div>
			<div class="input-control">
				<label for="password">Contraseña</label>
				<input id="password" name="password" type="password">
				<div class="error"></div>
			</div>
			<div class="input-control">
				<label for="password2">Confirmar Contraseña</label>
				<input id="password2" name="password2" type="password">
				<div class="error"></div>
			</div>
			<button class="button-2 btn" type="submit" @click="cambiarEstilo">Registrarse</button>
		</form>
		<div class="img-container">
			<img src="/img/fondo-noche.jpeg">
		</div>
	</div>
</template>
<script>
	export default {
		name: 'Contactanos',
		methods: {
			cambiarEstilo() {
				const form = document.getElementById('form');
				const username = document.getElementById('username');
				const email = document.getElementById('email');
				const password = document.getElementById('password');
				const password2 = document.getElementById('password2');

				form.addEventListener('submit', e => {
					e.preventDefault();

					validateInputs();
				});

				const setError = (element, message) => {
					const inputControl = element.parentElement;
					const errorDisplay = inputControl.querySelector('.error');

					errorDisplay.innerText = message;
					inputControl.classList.add('error');
					inputControl.classList.remove('success');
				};

				const setSuccess = element => {
					const inputControl = element.parentElement;
					const errorDisplay = inputControl.querySelector('.error');

					errorDisplay.innerText = '';
					inputControl.classList.add('success');
					inputControl.classList.remove('error');
				};

				const isValidEmail = email => {
					const re = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
					return re.test(String(email).toLowerCase());
				};

				const validateInputs = () => {
					const usernameValue = username.value.trim();
					const emailValue = email.value.trim();
					const passwordValue = password.value.trim();
					const password2Value = password2.value.trim();

					if (usernameValue === '') {
						setError(username, 'Usuario es requerido');
					} else {
						setSuccess(username);
					}

					if (emailValue === '') {
						setError(email, 'Correo Electronico es requerido');
					} else if (!isValidEmail(emailValue)) {
						setError(email, 'Ingrese un correo electronico valido');
					} else {
						setSuccess(email);
					}

					if (passwordValue === '') {
						setError(password, 'Contraseña es requerido');
					} else if (passwordValue.length < 8) {
						setError(password, 'Contraseña debe contar con 8 caracteres');
					} else {
						setSuccess(password);
					}

					if (password2Value === '') {
						setError(password2, 'Confirme su contraseña');
					} else if (password2Value !== passwordValue) {
						setError(password2, "Las contraseñas no coinciden");
					} else {
						setSuccess(password2);
					}

				};

			},
		},
	};
</script>

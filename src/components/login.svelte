<script>
	let password = $state('');
	let error = $state('');
	let { loginCompleted, password : PASS } = $props();

	const login = () => {
		if (password === PASS) {
			loginCompleted();
		} else {
			error = 'Onjuist, probeer opnieuw';
			password = '';
		}
	};

	const keyPress = (event) => {
		if (event.key === 'Enter') {
			event.preventDefault();
			login();
		}
	};
</script>

<div class="input">
	<input
		type="password"
		class="input-field"
		id="password"
		bind:value={password}
		onkeyup={keyPress}
		placeholder="Enter code..."
	/>
	<button class="btn" onclick={login}>Login</button>
</div>

{#if error}
	<div class="error">
		<h2>{error}</h2>
	</div>
{/if}

<style>
	.btn {
		color: var(--white);
		font-size: 1.1rem;
		padding: 0.7rem 1.5rem;
		border-radius: 0.3rem;
		background-color: var(--blue);
		border: none;
		position: absolute;
		right: 0.5rem;
		bottom: 0.5rem;
	}

	.input {
		position: relative;
		display: flex;
		width: 100%;
		justify-self: center;
	}

	.error {
		justify-self: center;
		color: var(--red);
	}

	.input-field {
		width: 100%;
		border: 0.06rem solid #d2d2d2bf;
		border-radius: 0.5rem;
		padding: 1.25rem;
		font-size: 1rem;
	}

	input[type='text']::placeholder {
		color: var(--grey);
	}
</style>

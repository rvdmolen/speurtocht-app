<script>
	import Login from './login.svelte';

  let password = 'aap';
	let { question, children } = $props();

	let locked = $state(true);

	const loginCompleted = () => {
		locked = false;
	};
</script>

<div class="question-container">
	{#if locked}
		<Login {loginCompleted} {password} />
	{:else}
		<div class="question">
			<h1>{question?.text}</h1>
			<h3>Stuur het antwoord door via whatsapp 😁 en jullie krijgen een letter!</h3>
			{@render children()}
		</div>
	{/if}
</div>

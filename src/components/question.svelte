<script>
	import Login from './login.svelte';

	let { question } = $props();
	let locked = $state(true);

	const loginCompleted = () => {
		locked = false;
	};
</script>

<div class="question-container">
	{#if locked}
		<Login {loginCompleted} />
	{:else}
		<div class="question">
			<h1>{question?.text}</h1>
			<h3>Stuur het antwoord via whatsapp</h3>
		</div>
	{/if}
</div>

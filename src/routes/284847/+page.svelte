<script>
	import Login from '../../components/login.svelte';
	import { questions } from '../../model/questions.js';

	let { text: questionText } = questions[1];
	let locked = $state(true);
	let question = $state(questionText);

	const loginCompleted = () => {
		locked = false;
	};
</script>

<div class="comp">
	{#if locked}
		<Login {loginCompleted} />
	{:else}
		<div class="question">
			<h1>{question}</h1>
			<h3>Stuur het antwoord via whatsapp</h3>
		</div>
	{/if}
</div>

<style>
	.comp {
		position: relative;
		display: grid;
		width: 50%;
		text-align: center;
	}

	@media only screen and (max-width: 600px) {
		.comp {
			width: 70%;
		}
	}
</style>

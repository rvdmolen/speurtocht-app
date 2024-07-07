<script>
	import Login from '../../components/login.svelte';
	import { questions } from '../../model/questions.js';

	let { text: questionText } = questions[2];
	let locked = true;
	let question = questionText;

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


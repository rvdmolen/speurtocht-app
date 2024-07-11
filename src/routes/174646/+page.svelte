<script>
	import Question from '../../components/question.svelte';
	import { questions } from '../../model/questions.js';


	import rebus1 from '$lib/assets/rebus1.png';
	import rebus2 from '$lib/assets/rebus2.png';

</script>

<Question question={questions[1]}>
	<div class="images">
		<img alt="Rebus1" src={rebus1} />
		<img alt="Rebus2" src={rebus2} />
	</div>
</Question>

<style>
	.images {
		display: flex;
		align-items: center;
		flex-direction: column;
		gap: 24px;
	}

	img {
		width: 90%;
	}
</style>


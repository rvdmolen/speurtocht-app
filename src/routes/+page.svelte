<script>
	import Login from '../components/login.svelte';

	let locked = $state(true);
    let password = 'admin';

	const loginCompleted = () => {
		locked = false;
	};
</script>


<div class="question-container">
    {#if locked}
        <Login {loginCompleted} {password} />
    {:else}
        <div class="summary">
            <a href="/174646">Vraag 1</a>
            <a href="/284847">Vraag 2</a>
            <a href="/375626">Vraag 3</a>
            <a href="/417364">Vraag 4</a>
            <a href="/593983">Vraag 5</a>
            <a href="/638233">Vraag 6</a>
            <a href="/732934">Vraag 7</a>
            <a href="/874623">Vraag 8</a>
            <a href="/973745">Vraag 9</a>
            <a href="/108632">Vraag 10</a>
            <a href="/117346">Vraag 11</a>
            <a href="/128484">Vraag 12</a>
            <a href="/137567">Vraag 13</a>
        </div>
    {/if}
</div>


<style>
	.summary {
		display: grid;
		gap: 10px;
	}

	a {
		color: var(--white);
	}
</style>

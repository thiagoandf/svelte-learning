<script>
	export let name;
	import Asynchronous from './components/Logic/Asynchronous.svelte';
	import ChainedLogic from './components/Logic/ChainedLogic.svelte';
	import Logic from './components/Logic/Logic.svelte';
	import Loops from './components/Logic/Loops.svelte';
	import Controller from './components/Props/Controller.svelte';
	import Reactivity from './components/Reactivity/Reactivity.svelte';
	import UpdatingArrays from './components/Reactivity/UpdatingArrays.svelte';

	let chapter = 0;

	function handlePrevious() {
		if (chapter > 0) chapter -= 1;
	}

	function handleNext() {
		if (chapter < 19) chapter += 1;
	}

</script>

<main>
	<h1>Hello {name}!</h1>
	<div>
		<button on:click={handlePrevious} disabled={chapter === 0}>
			{`< Previous`}
		</button>
		
		<button on:click={handleNext} disabled={chapter === 19}>
			{`Next >`}
		</button>
	</div>

	{#if chapter === 0}
	<Reactivity />
	<UpdatingArrays />
	{:else if chapter === 1}
	<Controller />
	{:else if chapter === 2}
	<Logic />
	<ChainedLogic />
	<Loops />
	<Asynchronous />
	{/if}
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>
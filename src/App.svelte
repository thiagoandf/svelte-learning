<script>
	export let name;
	import Logic from './components/Logic/Logic.svelte';
	import Controller from './components/Props/Controller.svelte';
	import Reactivity from './components/Reactivity/Reactivity.svelte';
	import UpdatingArrays from './components/Reactivity/UpdatingArrays.svelte';
</script>

<main>
	<h1>Hello {name}!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>

	<Reactivity />

	<UpdatingArrays />

	<Controller />

	<Logic />
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
<script>
	import { onMount } from 'svelte';
	import Home from './lib/pages/Home.svelte';
	import Settings from './lib/pages/Settings.svelte';

	let page;

	function onRouteChange() {
		const path = console.log(window.location.hash.slice(1));

		if (page === '/') {
			page = 'home';
		} else if (page === '/settings') {
			page = 'settings';
		} else {
			window.location.hash = '/';
		}

		onMount(onRouteChange);
	}
</script>

<svelte:window on:hashchange={onRouteChange} />

<nav>
	<a href="#/">Home</a>
	<a href="#/settings">Settings</a>
</nav>

{#if page === 'home'}
	<Home />
{:else if page === 'settings'}
	<Settings />
{/if}

<style>
</style>

<script>
	import { onMount } from 'svelte';
	import Home from './lib/pages/Home.svelte';
	import Settings from './lib/pages/Settings.svelte';

	let page;

	function onRouteChange() {
		const path = window.location.hash.slice(1);

		if (path === '/') {
			page = 'home';
		} else if (path === '/settings') {
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

<svelte:head>
	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
	<link
		href="https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@100;300;400;500;700&display=swap"
		rel="stylesheet"
	/>
</svelte:head>

{#if page === 'home'}
	<Home />
{:else if page === 'settings'}
	<Settings />
{/if}

<style>
</style>

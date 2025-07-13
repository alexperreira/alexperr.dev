<script lang="ts">
	import About from '$lib/About.svelte';
	import Navleft from '$lib/Navleft.svelte';
	let showAbout = false;
	const openAbout = () => (showAbout = true);
	const closeAbout = () => (showAbout = false);
	const goHome = () => (showAbout = false);
</script>

<div class="app">
	{#if showAbout}
		<About close={closeAbout} />
	{/if}
	<Navleft {showAbout} {openAbout} {goHome} />
</div>

<style>
	@import '../styles.css';
</style>

<script lang="ts">
	import { onDestroy, onMount } from 'svelte';
	import { fade } from 'svelte/transition';
	let { close }: { close: () => void } = $props();

	function handleKeydown(e: KeyboardEvent) {
		if (e.key === 'Escape') close();
	}

	onMount(() => {
		window.addEventListener('keydown', handleKeydown);
	});

	onDestroy(() => {
		window.addEventListener('keydown', handleKeydown);
	});
</script>

<div
	class="overlay"
	role="dialog"
	aria-label="About Section"
	in:fade={{ duration: 200 }}
	out:fade={{ duration: 200 }}
>
	<button class="close-icon" onclick={close} aria-label="back"></button>
	<div class="content">
		<div class="column column1">
			<h3>
				Specializing in refined digital web experiences with a focus on animated, responsive, and
				interactive content.
			</h3>
			<p>Partnering with agencies and brands with value design and development integrity.</p>
			<p>
				Delivering highly executed front-end user experience by paying close attention to the
				nuances of design, optimization, and performance.
			</p>
		</div>
		<div class="column column2">
			<h4>Availability</h4>
			<h5>June 2025 &mdash;</h5>
			<p>Remotely, Boise</p>
			<br />
			<h4>Services</h4>
			<h5>Development &mdash;</h5>
			<p>Technical Direction</p>
			<p>Front-end Development</p>
			<p>Craft CMS Solutions</p>
			<p>Development Consulting</p>
		</div>
		<div class="column column2">
			<h4>Tech Stack</h4>
			<h5>Front-end + Frameworks</h5>
			<p>HTML, CSS, JavaScript</p>
			<p>React</p>
			<p>Sveltekit</p>
			<h5>Back-end</h5>
			<p>Express.js, Supabase, MongoDB,</p>
			<p>Postgresql, SQL</p>
		</div>
	</div>
</div>

<style>
	.overlay {
		position: fixed;
		width: 100%;
		height: 100%;
		top: 0;
		left: 0;
		right: 0;
		bottom: 0;
		background-color: #6800ff40;
		z-index: 2;
		cursor: pointer;
		transition: 0.7s;
	}

	.close-icon {
		background-color: #6800ff00;
		background-image: url('/static/icons/close.svg');
		background-repeat: no-repeat;
		background-size: contain;
		position: absolute;
		top: 50px;
		right: 50px;
		cursor: pointer;
		height: 50px;
		width: 50px;
		border: none;
		border-radius: 50%;
	}

	.content {
		display: flex;
		width: 66%;
		max-width: 1100px;
		height: 600px;
		margin: 300px auto;
		color: #ffffff;
		font-family: 'Hanken Grotesk', sans-serif;
	}

	.column {
		margin: 20px;
	}

	.column h3 {
		font-size: 24px;
	}

	.column1 {
		width: 45%;
	}

	.column1 p {
		font-size: 20px;
		line-height: 34px;
	}

	.column2 {
		width: 25%;
	}

	.column2 h4 {
		font-size: 20px;
	}

	.column2 h5 {
		font-size: 18px;
		line-height: 16px;
		margin: 5px 0px;
	}

	.column2 p {
		font-size: 14px;
		line-height: 12px;
	}

	.column3 {
		width: 25%;
	}
</style>

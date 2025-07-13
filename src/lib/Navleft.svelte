<script lang="ts">
	let {
		openAbout,
		showAbout,
		goHome
	}: {
		openAbout: () => void;
		showAbout: boolean;
		goHome: () => void;
	} = $props();
</script>

<nav class="container" class:top-left={showAbout}>
	<button class="home-title" onclick={goHome} aria-label="home">
		<h1>alex<br />perr<br />.Dev</h1>
	</button>

	<div class="menu-container">
		<div class="column column1">
			<div class="row">
				<p><a href="https://github.com/alexperreira">Github</a></p>
			</div>
			<div class="row">
				<p><a href="https://www.linkedin.com/in/alexperr">Linkedin</a></p>
			</div>
		</div>
		<div class="column column2">
			<div class="row">
				<p>Boise Idaho</p>
			</div>
			<div class="row">
				<p>
					<a href="mailto:hello@alexperr.dev?subject=🤘 Hi Alex, I%27d like to work with you.">
						hello@alexperr.dev
					</a>
				</p>
			</div>
		</div>
		<div class="column column3">
			<div class="row">
				<p>
					<button onclick={openAbout} role="dialog" aria-label="About Section">About</button>
				</p>
			</div>
			<div class="row"><p>Journal</p></div>
		</div>
	</div>
</nav>

<style>
	nav {
		position: absolute;
		bottom: 0;
		left: 0;
		margin: 20px 60px;
		text-align: left;
		transform: translateY(0);
		transition: all 0.5s ease-in-out;
		cursor: pointer;
	}

	nav.top-left {
		top: 80vh;
		bottom: auto;
		transform: translateY(-80vh);
		z-index: 5;
	}
	h1 {
		font-family: 'Druk Wide Web Bold Regular';
		font-size: 48px;
		font-weight: 100;
		text-transform: uppercase;
		color: #ffffff;
		-webkit-text-stroke-width: 1px;
		-webkit-text-stroke-color: #ffffff;
		margin: 20px;
		transition: 0.5s;
	}

	h1:hover {
		color: #0f0f0f05;
		transition: 0.5s ease-in-out;
	}

	.menu-container {
		display: flex;
		color: #ffffff;
		font-family: 'Hanken Grotesk', sans-serif;
		font-optical-sizing: auto;
		font-weight: 500;
		font-style: normal;
		margin: 10px 0px 40px 0px;
	}

	.column {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: left;
		padding: 5px 20px;
	}

	.row {
		margin: 5px;
		height: 20px;
	}

	button {
		border: none;
		background: none;
		color: #ffffff;
		font-family: 'Hanken Grotesk', sans-serif;
		font-size: 16px;
		font-weight: 500;
		font-style: normal;
		padding-left: 0;
		cursor: pointer;
	}

	.row p {
		margin: 0;
	}

	a {
		color: #ffffff;
		text-decoration: none;
		font-size: 16px;
	}

	a:hover {
		transform: scaleX(0.5);
	}
</style>

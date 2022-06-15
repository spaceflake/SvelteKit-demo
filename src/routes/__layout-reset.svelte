<script>
	// @ts-ignore
	import Title from '$lib/title.svelte';
	import '../styles/global.css';
</script>

<header>
	<nav>
		<Title title="Spaceflake Game Guides" />
		<div class="links">
			<a href="/">Home</a>
			<a href="/about">About</a>
			<a href="/guides">Guides</a>
		</div>
	</nav>
</header>
<main>
	<!-- page content -->
	<slot />
</main>
<footer>
	<p>Copyright 2022 Spaceflake Gaming Guides</p>
</footer>

<style>
	header {
		text-align: center;
		background-color: rgba(0, 0, 0, 0.1);
	}
	main {
		width: min(100% - 1rem);
		max-width: 960px;
		margin: 20px auto;
		flex-grow: 1;
	}

	.links {
		margin-left: auto;
	}
	a {
		margin-left: 10px;
	}
	nav {
		display: flex;
		align-items: center;
		width: min(100% - 1rem);

		max-width: 960px;
		margin: 0 auto;
	}
	footer {
		margin-top: 1rem;
		text-align: center;
	}
</style>

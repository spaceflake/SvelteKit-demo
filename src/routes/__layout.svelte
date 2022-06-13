<script>
	// @ts-ignore
	import Title from '$lib/title.svelte';
	import '../styles/global.css';
</script>

<header>
	<Title title="Spaceflake Gaming Guides" />
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
		display: flex;
		justify-content: center;
	}
	main {
		flex-grow: 1;
		width: 100%;
		margin: 20px auto;
	}
	footer {
		text-align: center;
	}
</style>

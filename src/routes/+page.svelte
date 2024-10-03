<script>
	import '../app.scss';
	import { base } from '$app/paths';
</script>

<svelte:head>
	<title>Slide decks</title>
</svelte:head>
<main>
	<h1>Presentations:</h1>
	<ul>
		<li>
			<a href="{base}/responsive">Responsive Web design</a>
		</li>
		<li>
			<a href="{base}/scaleui2">ScaleUI 2.0</a>
		</li>
	</ul>
</main>

<style>
	main {
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	ul {
		list-style: none;
		padding: 0;
	}
	li {
		margin: 1rem 0;
	}
</style>

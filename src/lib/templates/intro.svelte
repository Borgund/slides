<script lang="ts">
	import Slide from '$lib/deck/slide.svelte';
	export let title = 'Title';
	export let subtitle = 'Subtitle';
	export let logo: string = 'scaleaq_logo.svg';
</script>

<Slide>
	<h1 class="r-stretch">{title}</h1>
	<p class="r-fit-text">{subtitle}</p>
	<img class="logo r-stretch" data-src={logo} alt="ScaleAQ logo" />
	<slot />
</Slide>

<style>
	.logo {
		margin: 8rem auto;
		max-width: 24rem;
	}
	p {
		color: var(--r-main-color);
	}
</style>

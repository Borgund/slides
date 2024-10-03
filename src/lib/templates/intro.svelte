<script lang="ts">
	import Slide from '$lib/deck/slide.svelte';
	export let title = 'Title';
	export let subtitle = 'Subtitle';
	export let logo: string = 'scaleaq_logo.svg';
</script>

<Slide>
    <p>{subtitle}</p>
	<h1 class="r-fit-text">{title}</h1>
	<img class="logo r-stretch" data-src={logo} alt="ScaleAQ logo" />
	<slot />
</Slide>

<style>
	.logo {
        margin: 8rem auto;
        max-width: 24rem;
	}
</style>

<script>
	import Code from '$lib/deck/code.svelte';
	import Slide from '$lib/deck/slide.svelte';
	import Intro from '$lib/templates/intro.svelte';
</script>

<Slide
	background_image="turborepo.png"
	background_options={{ size: 'cover', position: 'center', opacity: '0.5' }}
	text={{ color: 'deeppink', stroke: { width: '1px', color: 'cyan' } }}
	heading={{ color: 'cyan', stroke: { width: '3px', color: 'deeppink' } }}
>
	<Intro title="Turbocharged workflows" subtitle="Using Turborepo in mono and solo repos" />
</Slide>
<Slide className="asd">
	<p>ads</p>
</Slide>

<style>
</style>

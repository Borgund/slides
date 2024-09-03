<script lang="ts">
	import Code from '$lib/deck/code.svelte';
	import Markdown from '$lib/deck/markdown.svelte';
	import Slide from '$lib/deck/slide.svelte';
	import Aboutme from '$lib/deck/templates/aboutme.svelte';
	import Intro from '$lib/deck/templates/intro.svelte';
</script>

<Intro title="Responsive web design" subtitle="Introduction" />
<Aboutme />

<Slide branded>
	<p>
		Responsive web design is an approach to web design that makes web pages render well on a variety
		of devices and window or screen sizes.
	</p>
</Slide>

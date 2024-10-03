<script lang="ts">
	import Slide from '$lib/deck/slide.svelte';
	import Aboutme from '$lib/templates/aboutme.svelte';
	import Feedback from '$lib/templates/feedback.svelte';
	import Intro from '$lib/templates/intro.svelte';
</script>

<Intro title="Responsive web design" subtitle="Introduction" />
<Aboutme />

<Slide branded>
	<p>
		Responsive web design is an approach to web design that makes web pages render well on a variety
		of devices and window or screen sizes.
	</p>
</Slide>

<Slide>
	<Feedback />
</Slide>

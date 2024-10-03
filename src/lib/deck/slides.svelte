<script lang="ts">
	import Reveal from 'reveal.js';
	import Markdown from 'reveal.js/plugin/markdown/markdown';
	import Highlight from 'reveal.js/plugin/highlight/highlight';
	import Search from 'reveal.js/plugin/search/search';
	import Notes from 'reveal.js/plugin/notes/notes';
	import 'reveal.js/dist/reveal.css';
	import './themes/scaledarktheme.scss';
	import 'reveal.js/plugin/highlight/monokai.css';

	import { onMount } from 'svelte';

	onMount(() => {
		const deck = new Reveal({
			plugins: [Markdown, Highlight, Notes, Search],
			slideNumber: true,
			showNotes: false,
			controls: true,
			progress: true,
			history: true,
			center: true,
			controlsTutorial: false,
			autoPlayMedia: true,
			transition: 'slide',
			transitionSpeed: 'fast',
			backgroundTransition: 'slide',
			autoAnimateEasing: 'ease',
			autoAnimateDuration: 1,
			hideInactiveCursor: true,
			hideCursorTime: 1000
		}).initialize();
	});
</script>

<div class="reveal">
	<div class="slides">
		<slot />
	</div>
</div>

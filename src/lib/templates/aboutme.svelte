<script lang="ts">
	import Notes from '$lib/deck/notes.svelte';
	import Slide from '$lib/deck/slide.svelte';
	import Reachout from './reachout.svelte';
</script>

<Slide animate background_image="megOgSelma.JPG">
	<h1 class="r-fit-text">🙋 Hello!</h1>
	<p>i am 👤 <b>Adrian Borgund</b></p>
	<p>i work as 👨‍💻 <b>Front-end Tech Lead</b></p>
	<Reachout />
	<slot />
	<Notes>Here kan du skrive notater!</Notes>
</Slide>

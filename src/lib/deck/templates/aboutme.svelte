<script lang="ts">
	import Notes from '../notes.svelte';
	import Slide from '../slide.svelte';
</script>

<Slide animate background_image="megOgSelma.JPG">
	<h1 class="r-fit-text">🙋 Hello!</h1>
	<p>i am 👤 <b>Adrian Borgund</b></p>
	<p>i work as 👨‍💻 <b>Front-end Tech Lead</b></p>
	<div class="fragment custom blur">
		<p>feel free to reach out on:</p>
		<div class="flex">
			<div class="slack flex">
				<img class="icon" data-src="slack.png" alt="slack logo" />
				<p><a href="https://scaleaq.slack.com/archives/D07FGJJ5T7C">@adrian.borgund</a></p>
			</div>
		</div>
	</div>
	<slot />
	<Notes>Here kan du skrive notater!</Notes>
</Slide>

<style>
	.flex {
		display: flex;
		align-items: center;
		justify-content: center;
		gap: 1rem;
	}
	img.icon {
		width: 4rem;
		height: 4rem;
		padding: 0.75rem;
		background-color: white;
		border-radius: 1.5rem;
	}
	.slack {
		padding: 0 2.5rem;
		background-color: rgba(0, 0, 0, 0.5);
		border-radius: 5rem;
	}
</style>

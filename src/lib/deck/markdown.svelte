<script lang="ts">
	export let name = 'example.md';
	export let external = true;
</script>

{#if external}
	<section data-markdown={name}></section>
{:else}
	<section data-markdown>
		<div data-template>
			<slot />
		</div>
	</section>
{/if}

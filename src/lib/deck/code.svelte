<script lang="ts">
	export let id: string | null = null;
	export let lines: string | boolean | null = null;
	export let noespace: boolean = false;
	export let contenteditable: boolean = false;
	export let code: string | null = null;
</script>

<pre data-id={id || null}>
    <code
		data-trim
		data-line-numbers={lines || null}
		data-noescape={noespace || null}
		contenteditable={contenteditable || null}>
		{#if code}
			{code}
		{:else}
			<slot />
		{/if}
    </code>
</pre>

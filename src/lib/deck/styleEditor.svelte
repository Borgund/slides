<script>
	import Code from './code.svelte';

	export let style = '';
	export let template = '';
	export let showCode = true;
	let styleHTML = `<style class="code-editor" contenteditable="true">${style}</style>`;
</script>

<div class="livecode" class:showCode>
	{#if showCode}
		<div>
			<p>HTML</p>
			<pre class="markup">
				<code contenteditable="true" bind:textContent={template}></code>
			</pre>
		</div>
	{/if}
	<div class="css">
		<p>CSS</p>
		<pre>
			{@html styleHTML}
        </pre>
	</div>
	<div class="result">
		<p>Result</p>
		<div class="content">{@html template}</div>
	</div>
</div>

<style lang="scss">
	:global(style.code-editor) {
		display: block;
		height: 100%;
		white-space: pre-wrap;
		background-color: #2d2d2d;
		color: #ccc;
		padding: 1em;
		overflow: auto;
		border-radius: 0.25rem;
	}
	.livecode {
		display: grid;
		grid-gap: 1rem;
		margin: 0;
		padding: 0;
		grid-template-columns: 50% 50%;
		grid-template-rows: 1fr;
		max-height: 65vh;
	}
	.result .content{
		height: 100%;
		max-height: 100%;
		overflow-y: scroll;
		width: 100%;
		border: 2px dashed var(--r-selection-background-color);
		border-radius: 0.25rem;
		background-color: hsl(0 0% 100% / 0.8);
		background-blend-mode: color-burn;
	}
	.markup code{
		white-space: pre-wrap;
	}
	.css {
		pre {
			box-shadow: none;
		}
	}
	.showCode {
		grid-template-columns: 50% 50%;
		grid-template-rows: max-content 1fr;
		grid-template-areas:
			'b a'
			'c a';
		max-height: 70vh;

		.markup {
			grid-area: b;
		}

		.result {
			grid-area: a;
		}

		.css {
			grid-area: c;
		}
	}
</style>

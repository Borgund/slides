<script lang="ts">
	import Code from '$lib/deck/code.svelte';
	import Markdown from '$lib/deck/markdown.svelte';
	import Slide from '$lib/deck/slide.svelte';
	import StyleEditor from '$lib/deck/styleEditor.svelte';
	import Aboutme from '$lib/templates/aboutme.svelte';
	import Intro from '$lib/templates/intro.svelte';
</script>

<Intro title="Hello world i guess" subtitle="Subtitles! They do sure can be long! Oh boy!" />
<Aboutme />

<Slide branded>
	<p>Slide 1</p></Slide
>
<Slide background_color="pink">
	<p>Slide 2</p></Slide
>

<Slide>
	<Slide>Vertical slide 1</Slide>
	<Slide>Vertical slide 2</Slide>
</Slide>

<Slide>
	<Slide animate>
		<Code id="code">
			{`
            function lol(){
            
            }
            `}
		</Code>
	</Slide>
	<Slide animate>
		<Code id="code">
			{`
            function lol(){
            console.log('lol');
            }
            `}
		</Code>
	</Slide>
</Slide>

<Slide animate>
	<p>Transitions:</p>
	<div class="box" data-id="box-1"></div>
	<div class="box" data-id="box-2"></div>
	<div class="box" data-id="box-3"></div>
</Slide>
<Slide animate>
	<p>Transitions:</p>
	<div class="box circle" data-id="box-1"></div>
	<div class="box medium" data-id="box-2"></div>
	<div class="box large" data-id="box-3"></div>
</Slide>

<Markdown external></Markdown>

<Slide>
	<StyleEditor
		style={`.demo {
    color: red;
}
	`}
		template={
`<div class="demo">
    <p>Demo text</p>
    <p>Demo text2</p>
</div>`}
		showCode
	/>
</Slide>

<style>
	.box {
		width: 100px;
		height: 100px;
		background-color: grey;
		margin: 10px;
		&.medium {
			height: 100px;
			width: 200px;
			background-color: red;
		}
		&.large {
			height: 200px;
			width: 100%;
			background-color: blue;
		}
	}
	.circle {
		border-radius: 100%;
		background-color: pink;
	}
</style>

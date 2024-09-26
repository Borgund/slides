<script>
	import Slide from '$lib/deck/slide.svelte';
	import Intro from '$lib/deck/templates/intro.svelte';
</script>

<Slide>
	<Intro title="Hello world i guess" subtitle="Subtitles! They do sure can be long! Oh boy!" />
</Slide>

<Slide>
	<img class="logo r-stretch" data-src="/scaleui_logo.svg" alt="ScaleUI logo" />
	<Slide>Recently reached 1.0</Slide>
	<Slide>Awesome work by everyone involved</Slide>
	<Slide>But so far it has been built as «only» a React component library</Slide>
	<Slide
		>With design Tokens and Icons in separate packages to make parts of the design system usable in
		other frameworks.</Slide
	>
	<Slide>
		Since teams in ScaleAQ use both React and Angular this means either one framework is left behind
		or we have to maintain two separate component libraries for the same design systems.
	</Slide>
</Slide>

<Slide>So we figured it would be smart to rethink the approach</Slide>

<Slide animate>
	<h2>from</h2>
	<img class="logo r-stretch" data-src="/scaleui_logo.svg" alt="ScaleUI logo" />
	<h1>1.0</h1>
</Slide>

<Slide animate>
	<h2>to</h2>
	<img class="logo r-stretch" data-src="/scaleui_logo.svg" alt="ScaleUI logo" />
	<h1>2.0</h1>
</Slide>

<Slide animate>
	<p>How should we approach this when we have:</p>
	<Slide>
		<ul>
			<li class="fragment">
				One design system
				<ul>
					<li class="fragment">That should support multiple applications</li>
					<li class="fragment">made by teams using different frameworks</li>
					<li class="fragment">and therefore also potentially multiple component libraries</li>
				</ul>
			</li>
		</ul>
	</Slide>
</Slide>

<Slide>
	<Slide><h1>Enter</h1></Slide>
	<Slide>
		<img class="logo" src="/wc.png" alt="Web components logo" />
		<h2>Web Components</h2>
		<p class="fragment">or more specifically:</p></Slide
	>
	<Slide background_image="StencilJS_logo.png"></Slide>
</Slide>

<Slide>
	<Slide animate>
		<h2>But first</h2>
		<h2 data-id="wc">What are Web Components?</h2>
	</Slide>
	<Slide animate>
		<h2 data-id="wc">What are Web Components?</h2>
		<p>
			A set of web platform APIs that allow you to create new custom, reusable, encapsulated HTML
			tags to use in web pages and web apps.
		</p>
	</Slide>
	<Slide animate>
		<h2 data-id="wc">Why Web Components?</h2>
		<p>
			Custom components and widgets built on the Web Component standards will work across modern
			browsers, and can be used with any JavaScript library or framework that works with HTML.
		</p>
	</Slide>
</Slide>

<style>
	img.logo {
		max-width: 18rem;
	}
</style>

<script>
	import Code from '$lib/deck/code.svelte';
	import Slide from '$lib/deck/slide.svelte';
	import Intro from '$lib/deck/templates/intro.svelte';
	import Reachout from '$lib/deck/templates/reachout.svelte';
	import { Confetti } from 'svelte-confetti';
</script>

<Slide>
	<Intro title="Javascript Frameworks" subtitle="There sure are many of them" />
</Slide>

<Slide>
	<img class="logo r-stretch" data-src="/scaleui_logo.svg" alt="ScaleUI logo" />
	<Slide>Recently reached 1.0</Slide>
	<Slide>Awesome work by everyone involved</Slide>
	<Slide>But so far it has been built as «only» a <b>React</b> component library</Slide>
	<Slide
		>With design Tokens and Icons in separate packages to make parts of the design system usable in
		other frameworks.</Slide
	>
	<Slide>
		Since teams in <b>ScaleAQ</b> use both <b>React</b> and <b>Angular</b> this means either one
		framework is left behind or we have to maintain <b>two separate component libraries</b> for the same
		design systems.
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

<Slide>
	<Slide>Back to</Slide>
	<Slide background_image="StencilJS_logo.png"></Slide>
	<Slide background_color="#3C2CFF">
		Stencil is a <b>compiler</b> that generates <b>Web Components</b>
		<small>(or really, Custom Elements)</small>. Stencil combines some of the best concepts from the
		most popular frameworks into a relatively simple build-time tool.
	</Slide>
	<Slide background_color="#377cdc" animate>
		<img data-src="stencil/stencilsetup1.png" alt="" /></Slide
	>
	<Slide background_color="#377cdc" animate>
		<img data-src="stencil/stencilsetup2.png" alt="" />
	</Slide>
</Slide>

<Slide>
	<Slide>How to make a stencil component:</Slide>
	<Slide animate>
		<Code id="code">
			{`
			import { Component, Prop } from '@stencil/core';
			@Component({
				
			})
			export class MyComponent {
			
			}
            `}
		</Code>
	</Slide>
	<Slide animate>
		<Code id="code">
			{`
			import { Component, Prop } from '@stencil/core';
			@Component({
				tag: 'my-component',
				styleUrl: 'my-component.css',
				shadow: true,
			})
			export class MyComponent {
			
			}
            `}
		</Code>
	</Slide>
	<Slide animate>
		<Code id="code">
			{`
			import { Component, Prop } from '@stencil/core';
			@Component({
				tag: 'my-component',
				styleUrl: 'my-component.css',
				shadow: true,
			})
			export class MyComponent {
			@Prop() first: string;
			@Prop() last: string;
			render() {
				}
			}
            `}
		</Code>
	</Slide>
	<Slide animate>
		<Code id="code">
			{`
			import { Component, Prop } from '@stencil/core';
			@Component({
				tag: 'my-component',
				styleUrl: 'my-component.css',
				shadow: true,
			})
			export class MyComponent {
			@Prop() first: string;
			@Prop() last: string;
			render() {
				return (
				<p>Hello, Scale!</p>
				<p>I'm {last}. {first + " " + last}.</p>
				);}
			}
            `}
		</Code>
	</Slide>
</Slide>

<Slide>
	<Slide>How to use the output:</Slide>
	<Slide animate>
		<Code id="code">
			{`
		<!-- The output is a standard HTML element -->
		<my-component></my-component>
    	`}
		</Code>
	</Slide>
	<Slide animate>
		<Code id="code">
			{`
		<!-- The output is a standard HTML element -->
		<my-component first="James" last="Bond"></my-component>
    	`}
		</Code>
	</Slide>
	<Slide animate>
		<Code id="code">
			{`
		{/* Here we use the component in a TSX file */}
		<my-component first="James" last="Bond"></my-component>
        `}
		</Code>
	</Slide>
</Slide>

<Slide>
	<p>
		But to give a better developer experience we have made wrapper libraries for <b>React</b> and
		<b>Angular</b>.
	</p>
	<div><Confetti infinite /></div>
</Slide>

<Slide>
	<Slide>In react:</Slide>
	<Slide animate>
		<Code id="code">
			{`
			import { SuiButton, SuiTypography } 
			from "@scaleaq/scaleui-wc-react";

			export default function ProductCard({ product }: Props) {
			return (
				<div>
					<SuiTypography type="h2">{title}</SuiTypography>
						<SuiButton>Some flabbergasting text</SuiButton>
					<SuiButton onClick={() => addItem(product)}>
						Button text!
					</SuiButton>
				</div>);
				}
    	`}
		</Code>
	</Slide>
	<Slide background_color="white" iframe_background="http://localhost:5000/"></Slide>
</Slide>

<Slide>
	<Slide>In Angular:</Slide>
	<Slide animate>
		<Code id="code">
			{`
			import {
				ComponentLibraryModule,
				SuiButton,
			} from "@scaleaq/scaleui-wc-angular/dist/component-library";
			...
			@NgModule({
				declarations: [AppComponent],
				imports: [BrowserModule, AppRoutingModule, ComponentLibraryModule],
				providers: [SuiButton],
				bootstrap: [AppComponent],
			})
			export class AppModule {}
		`}
		</Code>
	</Slide>
	<Slide background_color="white" iframe_background="http://localhost:4000/"></Slide>
	<Slide>We are going to have working demos for both frameworks in place shortly(ish)</Slide>
</Slide>

<Slide>
	<Slide>
		<p>Do you want to contribute?</p>
		<p class="fragment">
			checkout<a href="https://github.com/scaleaq/scaleui-mono/tree/main" target="_blank"
				><img class="githublogo" height="32px" width="32px" src="githublogo.png" /> scaleui-mono</a
			>
		</p>
		<Reachout />
	</Slide>
</Slide>

<Slide>
	<p>Any questions?</p>
</Slide>
<Slide>
	<img class="logo r-stretch" data-src="scaleui_logo.svg" alt="ScaleUI logo" />
</Slide>

<style>
	small {
		font-size: 50%;
		line-height: 250%;
	}
	a {
		display: flex;
		justify-content: center;
		align-items: center;
		gap: 1rem;
	}
	.githublogo {
		filter: invert(1);
	}
	b {
		font-weight: 800;
		font-size: 120%;
	}
	img.logo {
		max-width: 18rem;
	}
</style>

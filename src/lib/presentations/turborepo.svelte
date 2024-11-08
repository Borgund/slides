<script>
	import Code from '$lib/deck/code.svelte';
	import Confettislide from '$lib/deck/confettislide.svelte';
	import Slide from '$lib/deck/slide.svelte';
	import Slides from '$lib/deck/slides.svelte';
	import Intro from '$lib/templates/intro.svelte';
</script>

<Slide
	background_image="turborepo.png"
	background_options={{ size: 'cover', position: 'center', opacity: '0.5' }}
	text={{ color: 'deeppink', stroke: { width: '1px', color: 'cyan' } }}
	heading={{ color: 'cyan', stroke: { width: '3px', color: 'deeppink' } }}
>
	<Intro title="Turbocharged workflows" subtitle="Using Turborepo in mono and solo repos" />
</Slide>
<Slide
	className="asd"
	heading={{ color: 'rebeccapurple', stroke: { color: 'cyan', width: '3px' } }}
>
	<h1>Turborepo</h1>
	<Slide>
		Turborepo is a high-performance build system for JavaScript and TypeScript codebases. It is
		designed for scaling monorepos and also makes workflows in single-package workspaces faster,
		too.
	</Slide>

	<Slide>
		<p>Lightweight monorepo tool:</p>
		<ul class="fragment">
			<li>Easily configured with npm or pnpm workspaces.</li>
			<li>Lets you organize packages how ever you like i.e. app and/or packages.</li>
			<li>
				Only needs to have at least one package json files and a turbo.json file to do it's magic
				🪄
			</li>
		</ul>
	</Slide>
	<Slide>
		<p>Ideal for scaling:</p>
		<ul class="fragment">
			<li>The more packages or apps in the repository, the more useful Turborepo becomes.</li>
			<li>Efficient workspace management across projects of all sizes.</li>
		</ul>
	</Slide>
	<Slide>
		<p>Versatile functionality:</p>
		<ul class="fragment">
			<li>This can also be leveraged in single-repo setups.</li>
			<li>I’ll demonstrate this flexibility today.</li>
		</ul>
	</Slide>
</Slide>

<Slide>
	<h2>Getting started</h2>
	<ol>
		<li>Either scaffold a demo repository:</li>
		<Code code="pnpm dlx create-turbo@latest" />
		<li>Or add to an existing repository</li>
		<Code code="pnpm add turbo --global" />
	</ol>
</Slide>

<Slide>
	<h2>Example monorepo structure</h2>
	<Code lines="1|4,7|4-6,7-14|15,18"
		>{`scaleui-mono/
  .
  ├── README.md
  ├── apps/
  │   ├── demo-angular/
  │   └── demo-react/
  ├── packages/
  │   ├── core/
  │   ├── eslint-config/
  │   ├── scaleui-icons/
  │   ├── scaleui-theme/
  │   ├── scaleui-wc-angular/
  │   ├── scaleui-wc-react/
  │   └── tsconfig
  ├── package.json
  ├── pnpm-lock.yaml
  ├── pnpm-workspace.yaml
  └── turbo.json`}
	</Code>
</Slide>

<Slide>
	<h2>Single repo setup</h2>
	<Code lines="1|4|5,7"
		>{`somerepo/
  .
  ├── README.md
  ├── src/
  ├── package.json
  ├── pnpm-lock.yaml
  └── turbo.json`}
	</Code>
</Slide>

<Slide animate>
	<h3 id="heading">Why would you use a monorepo tool for a single repository?</h3>
	<p class="fragment current-visible">Why not? 🤷‍♂️</p>
</Slide>

<Slide animate>
	Local and/or remote* caching support
	<Slide animate>
		<img data-src="/turborepo/caching.avif" />
		<p class="fragment">(*remote = 💰 to Vercel)</p>
	</Slide>
	<Slide>
		<img data-src="/turborepo/caching2.png" width="700px" />
	</Slide>
</Slide>
<Slide animate>
	<p>Task parallelization</p>
	<Slide animate>
		<img data-src="/turborepo/slow-tasks.avif" />
	</Slide>
	<Slide animate>
		<img data-src="/turborepo/turborepo-tasks.avif" />
	</Slide>
</Slide>

<Slide animate>
	Task sequential runner.
	<img data-src="/turborepo/neon-task.png" width="700px" />
</Slide>

<Slide animate>
	Boiler plate code generators.
	<img data-src="/turborepo/plop.jpg" width="700px" />
</Slide>
<Slide>
	👨‍💻 DEMO 👨‍💻
	<Confettislide></Confettislide>
</Slide>

<style>
</style>

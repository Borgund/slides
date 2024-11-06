<script lang="ts">
	export let id: string | null = null;
	export let className: string | null = null;
	export let animate: boolean = false;
	export let restart: boolean = false;
	export let background_color: string | null = null;
	export let gradient: { from: string; to: string; direction?: string } | null = null;
	export let background_image: string | null = null;
	export let background_options: {
		size?: string;
		position?: string;
		repeat?: string;
		opacity?: string;
	} | null = null;
	export let branded: boolean = false;
	export let iframe_background: string | null = null;
	export let video_background: string | null = null;
	export let video_background_options: {
		loop: string;
		muted: string;
	} | null = null;
	export let text: { color: string; stroke?: { width: string; color: string } } | null;
	export let heading: { color: string; stroke?: { width: string; color: string } } | null;
</script>

<section
	class={className ??
		'' +
			(branded ? 'branded' : '') +
			(text?.stroke ? ' text-stroke' : '') +
			(heading?.stroke ? ' heading-stroke' : '')}
	data-auto-animate-id={id}
	data-auto-animate={animate || null}
	data-auto-animate-restart={restart || null}
	data-background-color={background_color || null}
	data-background-gradient={(gradient &&
		`linear-gradient(${gradient.direction || 'to bottom'}, ${gradient.from}, ${gradient.to})`) ||
		null}
	data-background-image={background_image || null}
	data-background-size={(background_options && background_options.size) || null}
	data-background-position={(background_options && background_options.position) || null}
	data-background-repeat={(background_options && background_options.repeat) || null}
	data-background-opacity={(background_options && background_options.opacity) || null}
	data-background-iframe={iframe_background || null}
	data-background-video={video_background || null}
	data-background-video-loop={video_background_options && video_background_options.loop}
	data-background-video-muted={video_background_options && video_background_options.muted}
	data-preload
	style={`
	${text && text.color ? `--r-main-color: ${text.color}` : ''};
	${text && text.stroke ? `--text-stroke-width: ${text.stroke.width}; --text-stroke-color: ${text.stroke.color}; ` : ''};
	${heading && heading.color ? `--r-heading-color: ${heading.color}` : ''};
	${heading && heading.stroke ? `--heading-stroke-width: ${heading.stroke.width}; --heading-stroke-color: ${heading.stroke.color}; ` : ''};
	`}
>
	<slot />
</section>

<style>
	.text-stroke {
		& p {
			-webkit-text-stroke: var(--text-stroke-width) var(--text-stroke-color);
		}
	}
	.heading-stroke {
		& h1,
		& h2,
		& h3,
		& h4,
		& h5,
		& h6 {
			-webkit-text-stroke: var(--heading-stroke-width) var(--heading-stroke-color);
		}
	}
	p {
		color: var(--r-main-color);
	}
</style>

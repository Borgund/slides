<script lang="ts">
	export let id: string | null = null;
	export let animate: boolean = false;
	export let restart: boolean = false;
	export let background_color: string | null = null;
	export let gradient: { from: string; to: string; direction?: string } | null = null;
	export let background_image: string | null = null;
	export let background_options: {
		size: string;
		position: string;
		repeat: string;
		opacity: string;
	} | null = null;
	export let branded: boolean = false;
	export let iframe_background: string | null = null;
	export let video_background: string | null = null;
	export let video_background_options: {
		loop: string;
		muted: string;
	} | null = null;
</script>

<section
	class={branded ? 'branded' : ''}
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
>
	<slot />
</section>

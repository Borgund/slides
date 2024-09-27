<script type="ts">
	import { Confetti } from 'svelte-confetti';
	import Slide from './slide.svelte';
</script>

<Slide>
	<div
		style="
        position: fixed;
        top: 0; 
        left: 0;
        height: 100vh;
        width: 100vw;
        display: flex;
        justify-content: center;
        overflow: hidden;
        pointer-events: none;"
	>
		<slot />
		<Confetti
			x={[-5, 5]}
			y={[0, 0.1]}
			delay={[500, 2000]}
			infinite
			duration={5000}
			amount={200}
			fallDistance="100vh"
		/>
	</div>
</Slide>

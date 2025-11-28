<script lang="ts">
	import { intersect } from '@svelte-put/intersect';
	import { browser } from '$app/environment';

	type Direction = 'up' | 'down' | 'left' | 'right' | 'fade' | 'scale';

	let {
		direction = 'up' as Direction,
		duration = 600,
		delay = 0,
		threshold = 0.1,
		rootMargin = '0px 0px -50px 0px',
		class: className = '',
		children
	} = $props();

	let visible = $state(false);
	let prefersReducedMotion = $state(false);

	// Check for reduced motion preference
	if (browser) {
		const motionQuery = window.matchMedia('(prefers-reduced-motion: reduce)');
		prefersReducedMotion = motionQuery.matches;

		motionQuery.addEventListener('change', (e) => {
			prefersReducedMotion = e.matches;
		});
	}

	const baseClasses = 'transition-all ease-out';

	const hiddenClasses = {
		up: 'opacity-0 translate-y-12',
		down: 'opacity-0 -translate-y-12',
		left: 'opacity-0 translate-x-12',
		right: 'opacity-0 -translate-x-12',
		fade: 'opacity-0',
		scale: 'opacity-0 scale-95'
	};

	const visibleClasses = {
		up: 'opacity-100 translate-y-0',
		down: 'opacity-100 translate-y-0',
		left: 'opacity-100 translate-x-0',
		right: 'opacity-100 translate-x-0',
		fade: 'opacity-100',
		scale: 'opacity-100 scale-100'
	};

	// If user prefers reduced motion, show content immediately without animation
	let shouldAnimate = $derived(!prefersReducedMotion);
</script>

<div
	use:intersect={{ threshold, rootMargin }}
	onintersectonce={() => (visible = true)}
	class="{shouldAnimate ? baseClasses : ''} {visible || !shouldAnimate
		? visibleClasses[direction]
		: hiddenClasses[direction]} {className}"
	style:transition-duration={shouldAnimate ? `${duration}ms` : '0ms'}
	style:transition-delay={shouldAnimate ? `${delay}ms` : '0ms'}
>
	{@render children?.()}
</div>

<script lang="ts">
	let {
		class: className = '',
		animate = false
	}: { class?: string; animate?: boolean } = $props();
</script>

<svg
	class={`${className} ${animate ? 'float-animation' : ''}`}
	viewBox="0 0 64 64"
	fill="none"
	xmlns="http://www.w3.org/2000/svg"
>
	<!-- Shuttlecock feathers -->
	<path
		d="M32 8 L28 24 L32 20 L36 24 Z"
		fill="currentColor"
		opacity="0.3"
		stroke="currentColor"
		stroke-width="1"
	/>
	<path
		d="M32 8 L24 22 L28 24 L32 20 Z"
		fill="currentColor"
		opacity="0.2"
		stroke="currentColor"
		stroke-width="1"
	/>
	<path
		d="M32 8 L40 22 L36 24 L32 20 Z"
		fill="currentColor"
		opacity="0.2"
		stroke="currentColor"
		stroke-width="1"
	/>
	<!-- Cork base -->
	<circle cx="32" cy="28" r="6" fill="currentColor" opacity="0.5" />
	<circle cx="32" cy="28" r="4" fill="currentColor" opacity="0.7" />
</svg>

<style>
	@keyframes float {
		0%,
		100% {
			transform: translateY(0) rotate(-5deg);
		}
		50% {
			transform: translateY(-10px) rotate(5deg);
		}
	}

	.float-animation {
		animation: float 3s ease-in-out infinite;
	}
</style>

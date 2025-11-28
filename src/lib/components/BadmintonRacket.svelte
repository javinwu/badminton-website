<script lang="ts">
	let { class: className = '' }: { class?: string } = $props();
</script>

<svg
	class={className}
	viewBox="0 0 64 64"
	fill="none"
	xmlns="http://www.w3.org/2000/svg"
>
	<!-- Handle -->
	<rect x="28" y="40" width="8" height="20" rx="4" fill="currentColor" opacity="0.3" />
	<!-- Racket frame -->
	<circle cx="32" cy="24" r="14" stroke="currentColor" stroke-width="2" opacity="0.4" fill="none" />
	<!-- Strings (grid pattern) -->
	<line x1="32" y1="12" x2="32" y2="36" stroke="currentColor" opacity="0.2" stroke-width="0.5" />
	<line x1="28" y1="12" x2="28" y2="36" stroke="currentColor" opacity="0.2" stroke-width="0.5" />
	<line x1="36" y1="12" x2="36" y2="36" stroke="currentColor" opacity="0.2" stroke-width="0.5" />
	<line x1="20" y1="24" x2="44" y2="24" stroke="currentColor" opacity="0.2" stroke-width="0.5" />
	<line x1="20" y1="20" x2="44" y2="20" stroke="currentColor" opacity="0.2" stroke-width="0.5" />
	<line x1="20" y1="28" x2="44" y2="28" stroke="currentColor" opacity="0.2" stroke-width="0.5" />
</svg>

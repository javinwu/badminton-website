<script lang="ts">
	let { pulsing = false }: { pulsing?: boolean } = $props();
</script>

<div class="absolute inset-0 -z-10 overflow-hidden">
	<!-- Grid lines -->
	<div class="absolute inset-0 grid-bg"></div>

	<!-- Accent gradient spots -->
	<div
		class="absolute top-0 right-0 h-[500px] w-[500px] rounded-full bg-gradient-to-br from-green-500/5 via-transparent to-transparent blur-3xl"
	></div>
	<div
		class="absolute bottom-0 left-0 h-[400px] w-[400px] rounded-full bg-gradient-to-tr from-amber-500/5 via-transparent to-transparent blur-3xl"
	></div>

	{#if pulsing}
		<!-- Pulsing dots at intersections -->
		<div class="absolute inset-0 dot-matrix pulse-dot"></div>
	{/if}
</div>

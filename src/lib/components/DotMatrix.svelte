<script lang="ts">
	let {
		density = 'normal',
		pulse = false
	}: { density?: 'sparse' | 'normal' | 'dense'; pulse?: boolean } = $props();

	const sizes = {
		sparse: '32px 32px',
		normal: '24px 24px',
		dense: '16px 16px'
	};
</script>

<div
	class="absolute inset-0 -z-10"
	style="
		background-image: radial-gradient(circle, rgba(0, 100, 0, 0.05) 1px, transparent 1px);
		background-size: {sizes[density]};
	"
	class:pulse-dot={pulse}
></div>

<script lang="ts">
	import './layout.css';
	import favicon from '$lib/assets/favicon.svg';
	import GridBackground from '$lib/components/GridBackground.svelte';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="anonymous" />
	<link
		href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Playfair+Display:wght@400;600;700&display=swap"
		rel="stylesheet"
	/>
</svelte:head>

<div class="relative flex min-h-screen flex-col overflow-x-hidden bg-white font-sans">
	<GridBackground pulsing={false} />

	<!-- Minimal Nav Bar -->
	<nav
		class="fixed top-0 left-0 z-50 w-full border-b border-gray-100 bg-white/80 backdrop-blur-xl"
	>
		<div class="mx-auto flex max-w-7xl items-center justify-between px-6 py-4">
			<!-- Logo/Brand -->
			<a
				href="/"
				class="flex items-center gap-3 text-xl font-semibold tracking-tight text-gray-900 transition-opacity hover:opacity-70"
			>
				<img
					src="https://image.maxpreps.io/school-mascot/5/9/4/594e7f5d-3e25-480c-bc2c-c15cbf09c737.gif"
					alt="srv wolves logo"
					class="h-8 w-8 rounded-full object-cover"
				/>
				<span class="font-serif">SRV Badminton</span>
			</a>

			<!-- Nav Links -->
			<div class="flex items-center gap-8">
				<a
					href="/gallery"
					class="text-sm font-medium text-gray-600 transition-colors hover:text-gray-900"
				>
					Gallery
				</a>
				<div class="h-4 w-px bg-gray-200"></div>
				<a
					href="https://www.instagram.com/srvhsbadminton/"
					target="_blank"
					rel="noopener noreferrer"
					class="text-sm font-medium text-gray-600 transition-colors hover:text-gray-900"
				>
					Instagram
				</a>
			</div>
		</div>
	</nav>

	<!-- Nav spacer -->
	<div class="h-16"></div>

	{@render children()}

	<!-- Minimal Footer -->
	<footer class="mt-auto border-t border-gray-100 bg-white py-12">
		<div class="mx-auto max-w-7xl px-6">
			<div class="flex flex-col items-center justify-between gap-6 sm:flex-row">
				<div class="flex items-center gap-2 text-sm text-gray-500">
					<span>© 2025 San Ramon Valley Badminton</span>
					<span class="h-1 w-1 rounded-full bg-gray-300"></span>
					<span>All rights reserved</span>
				</div>
				<div class="text-sm text-gray-400">Made by Javin W</div>
			</div>
		</div>
	</footer>
</div>

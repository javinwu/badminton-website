<script lang="ts">
	import './layout.css';
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<div class="relative flex min-h-screen flex-col overflow-x-hidden bg-green-50 font-sans lowercase">
	<!-- Nav Bar -->
	<nav class="fixed top-0 left-0 z-50 w-full bg-[#006400] text-[#FFD700] shadow-md">
		<div class="mx-auto flex max-w-7xl items-center justify-between px-6 py-3">
			<a
				href="/gallery"
				class="rounded-full bg-[#FFD700] px-4 py-1 font-semibold text-[#006400] shadow-md transition hover:bg-white"
			>
				gallery
			</a>
		</div>
	</nav>

	<!-- LOGO HEADER -->
	<header
		class="pointer-events-none fixed top-0 left-0 z-50 flex w-full items-center justify-center bg-transparent py-4"
	>
		<a
			href="/"
			class="pointer-events-auto transition-transform duration-300 hover:scale-110 hover:opacity-80"
		>
			<img
				src="https://image.maxpreps.io/school-mascot/5/9/4/594e7f5d-3e25-480c-bc2c-c15cbf09c737.gif"
				alt="srv wolves logo"
				class="logo h-20 w-20 rounded-full border-2 border-[#FFD700] shadow-lg"
			/>
		</a>
	</header>

	<!-- MADE BY JAVIN W -->
	<div
		id="made-by"
		class="fixed top-4 right-4 z-50 text-sm font-medium tracking-wide text-[#006400]"
	>
		made by javin w
	</div>

	<!-- NAVBAR SPACER (keeps content from hiding behind navbar) -->
	<div class="h-[70px]"></div>

	{@render children()}

	<!-- Footer -->
	<footer id="footer" class="mt-auto bg-[#006400] py-6 text-center text-[#FFD700]">
		<p class="text-sm tracking-wide">© 2025 san ramon valley badminton • all rights reserved</p>
	</footer>
</div>

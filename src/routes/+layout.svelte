<script lang="ts">
	import './layout.css';
	import favicon from '$lib/assets/favicon.svg';
	import GridBackground from '$lib/components/GridBackground.svelte';
	import { beforeNavigate, afterNavigate } from '$app/navigation';
	import { page } from '$app/stores';
	import { fly, fade } from 'svelte/transition';
	import { cubicOut } from 'svelte/easing';

	let { children } = $props();

	let isNavigating = $state(false);
	let showContent = $state(true);
	let mobileMenuOpen = $state(false);

	beforeNavigate(() => {
		isNavigating = true;
		showContent = false;
		mobileMenuOpen = false;
	});

	afterNavigate(() => {
		setTimeout(() => {
			showContent = true;
			isNavigating = false;
		}, 320);
	});

	function toggleMobileMenu() {
		mobileMenuOpen = !mobileMenuOpen;
	}

	function closeMobileMenu() {
		mobileMenuOpen = false;
	}
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
		class="fixed top-0 left-0 z-50 w-full border-b border-gray-100 bg-white/80 backdrop-blur-xl shadow-sm"
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

			<!-- Desktop Nav Links (hidden on mobile) -->
			<div class="hidden md:flex items-center gap-8">
				<a
					href="/gallery"
					class="text-sm font-medium text-gray-600 transition-colors hover:text-green-600"
				>
					Gallery
				</a>
				<div class="h-4 w-px bg-gray-200"></div>
				<a
					href="/resources"
					class="text-sm font-medium text-gray-600 transition-colors hover:text-green-600"
				>
					Resources
				</a>
				<div class="h-4 w-px bg-gray-200"></div>
				<a
					href="https://www.instagram.com/srvhsbadminton/"
					target="_blank"
					rel="noopener noreferrer"
					class="text-sm font-medium text-gray-600 transition-colors hover:text-green-600"
				>
					Instagram
				</a>
			</div>

			<!-- Mobile Menu Hamburger -->
			<button
				onclick={toggleMobileMenu}
				class="md:hidden flex flex-col items-center justify-center w-10 h-10 gap-1.5 transition-all"
				aria-label="Toggle menu"
			>
				<span
					class="block h-0.5 w-6 bg-gray-700 transition-all duration-300"
					class:rotate-45={mobileMenuOpen}
					class:translate-y-2={mobileMenuOpen}
				></span>
				<span
					class="block h-0.5 w-6 bg-gray-700 transition-all duration-300"
					class:opacity-0={mobileMenuOpen}
				></span>
				<span
					class="block h-0.5 w-6 bg-gray-700 transition-all duration-300"
					class:-rotate-45={mobileMenuOpen}
					class:-translate-y-2={mobileMenuOpen}
				></span>
			</button>
		</div>
	</nav>

	<!-- Mobile Menu Drawer -->
	{#if mobileMenuOpen}
		<!-- Overlay -->
		<button
			transition:fade={{ duration: 300 }}
			onclick={closeMobileMenu}
			class="fixed inset-0 z-40 bg-black/40 md:hidden"
			aria-label="Close menu"
		></button>

		<!-- Drawer Content -->
		<div
			transition:fly={{ y: -300, duration: 400, easing: cubicOut }}
			class="fixed top-16 left-0 right-0 z-40 bg-white/95 backdrop-blur-xl border-b border-gray-200 shadow-2xl md:hidden"
		>
			<div class="flex flex-col px-6 pt-6 pb-8 space-y-1">
				<h2 class="text-xl font-semibold text-gray-900 mb-4 font-serif">Menu</h2>
				<a
					href="/gallery"
					onclick={closeMobileMenu}
					class="text-base font-medium text-gray-700 hover:text-green-600 transition-colors py-3 px-4 rounded-lg hover:bg-gray-50 active:bg-gray-100"
				>
					Gallery
				</a>
				<a
					href="/resources"
					onclick={closeMobileMenu}
					class="text-base font-medium text-gray-700 hover:text-green-600 transition-colors py-3 px-4 rounded-lg hover:bg-gray-50 active:bg-gray-100"
				>
					Resources
				</a>
				<a
					href="https://www.instagram.com/srvhsbadminton/"
					target="_blank"
					rel="noopener noreferrer"
					onclick={closeMobileMenu}
					class="text-base font-medium text-gray-700 hover:text-green-600 transition-colors py-3 px-4 rounded-lg hover:bg-gray-50 active:bg-gray-100"
				>
					Instagram
				</a>
			</div>
		</div>
	{/if}

	<!-- Nav spacer -->
	<div class="h-16"></div>

	{#if showContent}
		<div
			in:fly={{ x: -25, duration: 100, opacity: 0 }}
			out:fly={{ y: -25, duration: 100, opacity: 0 }}
		>
			{@render children()}
		</div>
	{/if}

	<!-- Minimal Footer -->
	<footer class="mt-auto border-t border-gray-100 bg-gradient-to-br from-white via-green-50/20 to-amber-50/20 py-12">
		<div class="mx-auto max-w-7xl px-6">
			<div class="flex flex-col items-center justify-between gap-6 sm:flex-row">
				<div class="flex items-center gap-2 text-sm text-gray-500">
					<span>© 2025 San Ramon Valley Badminton</span>
					<span class="h-1 w-1 rounded-full bg-gradient-to-r from-green-600 to-amber-500"></span>
					<span>All rights reserved</span>
				</div>
				<div class="text-sm text-gray-400">Made by Javin W</div>
			</div>
		</div>
	</footer>
</div>

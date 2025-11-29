<script lang="ts">
	import './layout.css';
	import favicon from '$lib/assets/favicon.svg';
	import GridBackground from '$lib/components/GridBackground.svelte';
	import { beforeNavigate, afterNavigate } from '$app/navigation';
	import { page } from '$app/stores';
	import { fly, fade } from 'svelte/transition';
	import { cubicIn, cubicOut } from 'svelte/easing';

	let { children } = $props();

	let isNavigating = $state(false);
	let showContent = $state(true);
	let mobileMenuOpen = $state(false);

	// Desktop navbar sliding indicator
	let navLinksContainer: HTMLDivElement;
	let indicatorStyle = $state('');

	const navItems = [
		{ href: '/announcements', label: 'Announcements' },
		{ href: '/gallery', label: 'Gallery' },
		{ href: '/resources', label: 'Resources' },
		{ href: 'https://www.instagram.com/srvhsbadminton/', label: 'Instagram', external: true }
	];

	function updateIndicator() {
		if (!navLinksContainer) return;

		const currentPath = $page.url.pathname;
		const links = navLinksContainer.querySelectorAll('a');

		let activeLink: HTMLAnchorElement | null = null;
		links.forEach((link) => {
			const href = link.getAttribute('href') || '';
			if (!href.startsWith('http') && currentPath === href) {
				activeLink = link as HTMLAnchorElement;
			}
		});

		if (activeLink) {
			const containerRect = navLinksContainer.getBoundingClientRect();
			const linkRect = activeLink.getBoundingClientRect();
			const left = linkRect.left - containerRect.left;
			const width = linkRect.width;
			indicatorStyle = `left: ${left}px; width: ${width}px; opacity: 1;`;
		} else {
			indicatorStyle = 'opacity: 0;';
		}
	}

	$effect(() => {
		$page.url.pathname;
		updateIndicator();
	});

	beforeNavigate(() => {
		isNavigating = true;
		showContent = false;
		mobileMenuOpen = false;
	});

	afterNavigate(() => {
		setTimeout(() => {
			showContent = true;
			isNavigating = false;
			updateIndicator();
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

	<!-- Enhanced Nav Bar -->
	<nav
		class="fixed top-0 left-0 z-50 w-full border-b border-gray-200/60 bg-white/80 backdrop-blur-xl"
	>
		<div class="mx-auto flex max-w-7xl items-center justify-between px-6 py-4">
			<!-- Logo/Brand -->
			<a
				href="/"
				class="flex items-center gap-3 text-xl font-bold tracking-tight text-gray-900 transition-all duration-200 hover:scale-105 group"
			>
				<div class="relative">
					<img
						src="https://image.maxpreps.io/school-mascot/5/9/4/594e7f5d-3e25-480c-bc2c-c15cbf09c737.gif"
						alt="srv wolves logo"
						class="h-9 w-9 rounded-full object-cover ring-2 ring-gray-200 group-hover:ring-green-500 transition-all duration-200"
					/>
				</div>
				<span class="font-serif bg-gradient-to-r from-gray-900 to-gray-700 bg-clip-text text-transparent">SRV Badminton</span>
			</a>

			<!-- Desktop Nav Links (hidden on mobile) -->
			<div class="hidden md:flex items-center gap-1 relative" bind:this={navLinksContainer}>
				{#each navItems as item, i}
					{#if i > 0}
						<div class="h-4 w-px bg-gray-200 mx-3"></div>
					{/if}
					<a
						href={item.href}
						target={item.external ? '_blank' : undefined}
						rel={item.external ? 'noopener noreferrer' : undefined}
						class="relative px-3 py-2 text-sm font-semibold text-gray-700 transition-all duration-200 hover:text-green-600 rounded-lg hover:bg-green-50/50"
						class:text-green-700={!item.external && $page.url.pathname === item.href}
					>
						{item.label}
					</a>
				{/each}

				<!-- Sliding indicator -->
				<div
					class="absolute bottom-0 h-0.5 bg-gradient-to-r from-green-600 to-amber-500 rounded-full transition-all duration-300 ease-out"
					style={indicatorStyle}
				></div>
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
					href="/announcements"
					onclick={closeMobileMenu}
					class="text-base font-medium text-gray-700 hover:text-green-600 transition-colors py-3 px-4 rounded-lg hover:bg-gray-50 active:bg-gray-100"
				>
					Announcements
				</a>
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
			in:fly={{ x: -30, duration: 150, easing: cubicIn }}
			out:fly={{ y: -30, duration: 150, easing: cubicOut }}
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

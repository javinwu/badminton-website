<script lang="ts">
	import ScrollReveal from '$lib/components/ScrollReveal.svelte';
	import DotMatrix from '$lib/components/DotMatrix.svelte';

	// ═══════════════════════════════════════════════════════════════
	// EDIT ANNOUNCEMENTS HERE - Add, remove, or modify as needed!
	// ═══════════════════════════════════════════════════════════════

	const announcements = [
		{
			id: 1,
			title: 'Season Tryouts Coming Soon!',
			date: '2025-12-15',
			category: 'Team',
			color: 'green',
			description:
				'Competitive team tryouts will be held on January 10-12. All skill levels welcome! Bring your racket and athletic shoes.',
			link: 'https://sites.google.com/view/srvhsbirdies/about/team-interest-form?authuser=0',
			linkText: 'Sign Up for Tryouts',
			featured: true
		},
		{
			id: 2,
			title: 'New Practice Schedule',
			date: '2025-12-01',
			category: 'Club',
			color: 'amber',
			description:
				'Club practices are now every Tuesday and Thursday from 3:30-5:30 PM in the main gym. Open to all members!',
			featured: false
		},
		{
			id: 3,
			title: 'Merch Store Now Open',
			date: '2025-11-20',
			category: 'General',
			color: 'blue',
			description:
				'Show your Wolves pride! New badminton team gear is available including jerseys, hoodies, and more.',
			link: 'https://bluechipathletic.com/collections/san-ramon-valley-badminton',
			linkText: 'Shop Now',
			featured: false
		},
	];

	// Sort announcements by date (newest first) and featured status
	const sortedAnnouncements = announcements.sort((a, b) => {
		if (a.featured && !b.featured) return -1;
		if (!a.featured && b.featured) return 1;
		return new Date(b.date).getTime() - new Date(a.date).getTime();
	});

	function formatDate(dateString: string) {
		const date = new Date(dateString);
		return date.toLocaleDateString('en-US', { month: 'long', day: 'numeric', year: 'numeric' });
	}

	function getColorClasses(color: string) {
		const colors = {
			green: {
				bg: 'from-green-50 to-green-100/50',
				border: 'border-green-600/20',
				text: 'text-green-600',
				hover: 'hover:border-green-600/40',
				badge: 'bg-green-100 text-green-700'
			},
			amber: {
				bg: 'from-amber-50 to-amber-100/50',
				border: 'border-amber-600/20',
				text: 'text-amber-600',
				hover: 'hover:border-amber-600/40',
				badge: 'bg-amber-100 text-amber-700'
			},
			blue: {
				bg: 'from-blue-50 to-blue-100/50',
				border: 'border-blue-600/20',
				text: 'text-blue-600',
				hover: 'hover:border-blue-600/40',
				badge: 'bg-blue-100 text-blue-700'
			}
		};
		return colors[color as keyof typeof colors] || colors.green;
	}
</script>

<svelte:head>
	<title>Announcements - SRV Badminton</title>
	<meta
		name="description"
		content="Latest news and announcements for San Ramon Valley High School Badminton"
	/>
</svelte:head>

<main class="flex-grow">
	<!-- HERO SECTION -->
	<section class="relative mx-auto max-w-7xl px-6 py-24 md:py-32">
		<div class="absolute inset-0 -z-10">
			<div class="absolute inset-y-0 left-1/4 w-px bg-gradient-to-b from-transparent via-gray-200 to-transparent"></div>
			<div class="absolute inset-y-0 right-1/4 w-px bg-gradient-to-b from-transparent via-gray-200 to-transparent"></div>
		</div>

		<ScrollReveal direction="up" duration={600} threshold={0.2}>
			<div class="text-center">
				<div class="mb-4 flex items-center justify-center gap-2">
					<div class="h-px w-12 bg-gradient-to-r from-transparent via-green-600 to-amber-500"></div>
					<span class="text-sm font-medium uppercase tracking-wider text-gray-500">Latest News</span>
					<div class="h-px w-12 bg-gradient-to-r from-amber-500 via-green-600 to-transparent"></div>
				</div>
				<h1
					class="bg-gradient-to-br from-gray-900 via-green-900 to-gray-900 bg-clip-text font-serif text-5xl font-bold tracking-tight text-transparent md:text-7xl"
				>
					Announcements
				</h1>
				<p class="mx-auto mt-6 max-w-2xl text-lg text-gray-600">
					Stay up to date with the latest news, events, and updates from SRV Badminton
				</p>

				<!-- Compact Remind Link -->
				<div class="mt-6">
					<a
						href="https://www.remind.com/join/YOURCODE"
						target="_blank"
						rel="noopener noreferrer"
						class="inline-flex items-center gap-2 rounded-lg border border-green-600/30 bg-green-50/50 px-4 py-2 text-sm font-medium text-green-700 transition-all hover:border-green-600 hover:bg-green-100 hover:text-green-800"
					>
						<svg class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9"
							/>
						</svg>
						<span>Get notifications via Remind</span>
					</a>
				</div>
			</div>
		</ScrollReveal>
	</section>

	<!-- ANNOUNCEMENTS GRID -->
	<section class="relative mx-auto max-w-7xl px-6 pb-24">
		<div class="grid gap-6 md:grid-cols-2">
			{#each sortedAnnouncements as announcement, i}
				<ScrollReveal direction="up" duration={600} delay={i * 100} threshold={0.1}>
					<div
						class="group relative overflow-hidden rounded-2xl border bg-white p-8 transition-all {getColorClasses(announcement.color).border} {getColorClasses(announcement.color).hover} hover:shadow-xl"
					>
						<!-- Background decoration -->
						<div class="absolute right-0 top-0 h-32 w-32 -translate-y-8 translate-x-8 opacity-0 transition-opacity group-hover:opacity-100">
							<DotMatrix density="sparse" pulse={false} />
						</div>

						<!-- Featured badge -->
						{#if announcement.featured}
							<div class="absolute right-4 top-4">
								<div
									class="flex items-center gap-1.5 rounded-full px-3 py-1 text-xs font-semibold {getColorClasses(announcement.color).badge}"
								>
									<svg class="h-3 w-3" fill="currentColor" viewBox="0 0 20 20">
										<path
											d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"
										/>
									</svg>
									Featured
								</div>
							</div>
						{/if}

						<!-- Content -->
						<div class="relative space-y-4">
							<!-- Category & Date -->
							<div class="flex items-center gap-3 text-sm text-gray-500">
								<span
									class="rounded-lg border px-3 py-1 font-medium {getColorClasses(announcement.color).border} {getColorClasses(announcement.color).text}"
								>
									{announcement.category}
								</span>
								<span class="flex items-center gap-1.5">
									<svg class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
										<path
											stroke-linecap="round"
											stroke-linejoin="round"
											stroke-width="2"
											d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z"
										/>
									</svg>
									{formatDate(announcement.date)}
								</span>
							</div>

							<!-- Title -->
							<h2
								class="font-serif text-2xl font-bold text-gray-900 transition-colors {getColorClasses(announcement.color).text} group-hover:{getColorClasses(announcement.color).text}"
							>
								{announcement.title}
							</h2>

							<!-- Description -->
							<p class="leading-relaxed text-gray-600">
								{announcement.description}
							</p>

							<!-- Link -->
							{#if announcement.link}
								<a
									href={announcement.link}
									target="_blank"
									rel="noopener noreferrer"
									class="inline-flex items-center gap-2 font-medium transition-transform group-hover:translate-x-1 {getColorClasses(announcement.color).text}"
								>
									<span>{announcement.linkText || 'Learn More'}</span>
									<svg class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
										<path
											stroke-linecap="round"
											stroke-linejoin="round"
											stroke-width="2"
											d="M9 5l7 7-7 7"
										/>
									</svg>
								</a>
							{/if}
						</div>
					</div>
				</ScrollReveal>
			{/each}
		</div>

		<!-- Empty state -->
		{#if announcements.length === 0}
			<div class="py-24 text-center">
				<div
					class="mx-auto mb-4 flex h-16 w-16 items-center justify-center rounded-full bg-gray-100"
				>
					<svg class="h-8 w-8 text-gray-400" fill="none" viewBox="0 0 24 24" stroke="currentColor">
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9"
						/>
					</svg>
				</div>
				<h3 class="mb-2 font-serif text-2xl font-bold text-gray-900">No announcements yet</h3>
				<p class="text-gray-600">Check back soon for updates!</p>
			</div>
		{/if}
	</section>

</main>

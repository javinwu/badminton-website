<script lang="ts">
	import ScrollReveal from '$lib/components/ScrollReveal.svelte';
	import DotMatrix from '$lib/components/DotMatrix.svelte';
</script>

<svelte:head>
	<title>Resources — SRV Badminton</title>
</svelte:head>

<main class="flex-grow">
	<!-- HERO SECTION -->
	<section class="relative mx-auto max-w-7xl px-6 py-32 md:py-40">
		<!-- Decorative elements -->
		<div class="absolute left-10 top-24 text-green-600/8">
			<svg class="h-16 w-16 rotate-12" viewBox="0 0 64 64" fill="none" xmlns="http://www.w3.org/2000/svg">
				<circle cx="32" cy="20" r="6" fill="currentColor" />
				<path d="M32 26 L28 45 L32 42 L36 45 Z" fill="currentColor" opacity="0.6" />
				<path d="M32 26 L24 42 L28 40 L32 42 Z" fill="currentColor" opacity="0.4" />
				<path d="M32 26 L40 42 L36 40 L32 42 Z" fill="currentColor" opacity="0.4" />
			</svg>
		</div>
		<div class="absolute right-16 top-32 text-amber-600/8">
			<svg class="h-20 w-20 -rotate-45" viewBox="0 0 64 64" fill="none" xmlns="http://www.w3.org/2000/svg">
				<rect x="28" y="40" width="8" height="20" rx="4" fill="currentColor" opacity="0.5" />
				<circle cx="32" cy="24" r="14" stroke="currentColor" stroke-width="2.5" fill="none" />
				<line x1="32" y1="12" x2="32" y2="36" stroke="currentColor" opacity="0.3" stroke-width="0.8" />
				<line x1="26" y1="12" x2="26" y2="36" stroke="currentColor" opacity="0.3" stroke-width="0.8" />
				<line x1="38" y1="12" x2="38" y2="36" stroke="currentColor" opacity="0.3" stroke-width="0.8" />
				<line x1="20" y1="24" x2="44" y2="24" stroke="currentColor" opacity="0.3" stroke-width="0.8" />
				<line x1="20" y1="18" x2="44" y2="18" stroke="currentColor" opacity="0.3" stroke-width="0.8" />
				<line x1="20" y1="30" x2="44" y2="30" stroke="currentColor" opacity="0.3" stroke-width="0.8" />
			</svg>
		</div>

		<div class="text-center">
			<div class="mb-6 flex items-center justify-center gap-3">
				<div class="h-px w-12 bg-gradient-to-r from-transparent via-green-600 to-amber-500"></div>
				<span class="text-sm font-medium uppercase tracking-wider text-gray-500"
					>Information</span
				>
				<div class="h-px w-12 bg-gradient-to-r from-amber-500 via-green-600 to-transparent"></div>
			</div>
			<h1
				class="bg-gradient-to-br from-gray-900 via-green-900 to-gray-900 bg-clip-text font-serif text-5xl font-bold leading-tight tracking-tight text-transparent md:text-6xl lg:text-7xl"
			>
				Resources
			</h1>
			<p class="mx-auto mt-6 max-w-2xl text-lg leading-relaxed text-gray-600">
				Everything you need to know about joining our team and club. Find answers to common
				questions and get started.
			</p>
		</div>
	</section>

	<!-- FAQ SECTION -->
	<section class="relative mx-auto max-w-4xl px-6 py-16">
		<div class="space-y-8">
			<!-- Question 1 -->
			<ScrollReveal direction="scale" duration={800} threshold={0.2}>
				<div
					class="group relative overflow-hidden rounded-2xl border border-gray-200 bg-white p-8 transition-all hover:border-green-600/20 hover:shadow-lg"
				>
					<div class="absolute right-0 top-0 h-24 w-24 -translate-y-6 translate-x-6">
						<DotMatrix density="sparse" pulse={false} />
					</div>
					<div class="relative space-y-4">
						<h2 class="font-serif text-2xl font-bold text-gray-900">
							What forms do I need to fill out?
						</h2>
						<p class="leading-relaxed text-gray-600">
							The only form you have to fill out is an athletic clearance form to ensure that you're
							healthy enough to play (only required for team).
						</p>
						<a
							href="https://athleticclearance.com/"
							target="_blank"
							rel="noopener noreferrer"
							class="inline-flex items-center gap-2 rounded-lg border border-gray-200 bg-white px-6 py-3 text-sm font-medium text-gray-900 transition-all hover:border-green-600 hover:bg-green-50 hover:text-green-900"
						>
							<span>Complete Athletic Clearance</span>
							<svg
								class="h-4 w-4 transition-transform group-hover:translate-x-0.5"
								fill="none"
								viewBox="0 0 24 24"
								stroke="currentColor"
							>
								<path
									stroke-linecap="round"
									stroke-linejoin="round"
									stroke-width="2"
									d="M14 5l7 7m0 0l-7 7m7-7H3"
								/>
							</svg>
						</a>
					</div>
				</div>
			</ScrollReveal>

			<!-- Question 2 -->
			<ScrollReveal direction="scale" duration={800} threshold={0.2}>
				<div
					class="group relative overflow-hidden rounded-2xl border border-gray-200 bg-white p-8 transition-all hover:border-green-600/20 hover:shadow-lg"
				>
					<div class="absolute right-0 top-0 h-24 w-24 -translate-y-6 translate-x-6">
						<DotMatrix density="sparse" pulse={false} />
					</div>
					<div class="relative space-y-4">
						<h2 class="font-serif text-2xl font-bold text-gray-900">How do I join the team?</h2>
						<p class="leading-relaxed text-gray-600">
							Tryouts are held for one week during February. Make sure to also complete the athletic
							clearance form to ensure that we can let you on the team. More information to come.
						</p>
					</div>
				</div>
			</ScrollReveal>

			<!-- Question 3 -->
			<ScrollReveal direction="scale" duration={800} threshold={0.2}>
				<div
					class="group relative overflow-hidden rounded-2xl border border-gray-200 bg-white p-8 transition-all hover:border-green-600/20 hover:shadow-lg"
				>
					<div class="absolute right-0 top-0 h-24 w-24 -translate-y-6 translate-x-6">
						<DotMatrix density="sparse" pulse={false} />
					</div>
					<div class="relative space-y-4">
						<h2 class="font-serif text-2xl font-bold text-gray-900">
							What experience do I need to join?
						</h2>
						<p class="leading-relaxed text-gray-600">
							No experience is required to join the club or even come to practice or training
							sessions. Anyone is welcome! To join the team you will need to tryout first. The first
							tryout date for the team is currently scheduled for February 6, 2025. More dates to
							come.
						</p>
					</div>
				</div>
			</ScrollReveal>

			<!-- Question 4 -->
			<ScrollReveal direction="scale" duration={800} threshold={0.2}>
				<div
					class="group relative overflow-hidden rounded-2xl border border-gray-200 bg-white p-8 transition-all hover:border-amber-600/20 hover:shadow-lg"
				>
					<div class="absolute right-0 top-0 h-24 w-24 -translate-y-6 translate-x-6">
						<DotMatrix density="sparse" pulse={false} />
					</div>
					<div class="relative space-y-4">
						<h2 class="font-serif text-2xl font-bold text-gray-900">
							What equipment is provided?
						</h2>
						<div class="space-y-3 leading-relaxed text-gray-600">
							<p class="font-semibold text-gray-900">
								List of recommended equipment and clothing:
							</p>
							<ul class="ml-6 space-y-2 list-disc">
								<li>
									If shopping for a racket on Amazon, find "joybadminton" under the sellers list as
									they are reliable
									<ul class="ml-6 mt-2 space-y-1 list-circle">
										<li>Arcsaber and Nanoflare rackets are good light rackets</li>
										<li>Astrox good heavier racket</li>
									</ul>
								</li>
								<li>Athletic shoes with rubber soles</li>
								<li>
									Clothing: SRV Badminton shirt with black shorts (preferably, if not pants/leggings)
									for game days
								</li>
							</ul>
							<p class="mt-4 text-sm italic text-gray-500">
								Note: If you would like to donate birdies, we are looking for Yonex Mavis 350 Medium
								Speed birdies
							</p>
						</div>
					</div>
				</div>
			</ScrollReveal>

			<!-- Question 5 -->
			<ScrollReveal direction="scale" duration={800} threshold={0.2}>
				<div
					class="group relative overflow-hidden rounded-2xl border border-gray-200 bg-white p-8 transition-all hover:border-amber-600/20 hover:shadow-lg"
				>
					<div class="absolute right-0 top-0 h-24 w-24 -translate-y-6 translate-x-6">
						<DotMatrix density="sparse" pulse={false} />
					</div>
					<div class="relative space-y-4">
						<h2 class="font-serif text-2xl font-bold text-gray-900">
							When does the season take place?
						</h2>
						<div class="space-y-3 leading-relaxed text-gray-600">
							<p>
								Exact dates for the 2024-2025 season have not been determined fully yet. Tentative
								season details are listed below:
							</p>
							<ul class="ml-6 space-y-2 list-disc">
								<li>Tryouts start on February 6, 2025</li>
								<li>Season will end around early-May</li>
								<li>Practices will be held on Mondays, Wednesdays, and Fridays</li>
								<li>
									Games will usually happen on Tuesdays and Thursdays (if no game, then expect
									practice)
								</li>
								<li>
									Days and times are tentative to change so please check your email to stay up to
									date
								</li>
							</ul>
						</div>
					</div>
				</div>
			</ScrollReveal>
		</div>
	</section>
</main>

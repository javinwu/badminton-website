<script lang="ts">
	import DotMatrix from '$lib/components/DotMatrix.svelte';
	import BadmintonShuttlecock from '$lib/components/BadmintonShuttlecock.svelte';
	import BadmintonRacket from '$lib/components/BadmintonRacket.svelte';
</script>

<main class="flex-grow">
	<!-- HERO SECTION -->
	<section class="relative mx-auto max-w-7xl px-6 py-32 md:py-48">
		<!-- Floating shuttlecock decorations -->
		<div class="pointer-events-none absolute left-10 top-20 text-green-600/20">
			<BadmintonShuttlecock class="h-16 w-16" animate={true} />
		</div>
		<div class="pointer-events-none absolute right-20 top-40 text-amber-600/20">
			<BadmintonShuttlecock class="h-12 w-12" animate={true} />
		</div>

		<div class="flex flex-col items-center gap-16 md:flex-row md:items-start md:gap-24">
			<!-- Hero Text -->
			<div class="flex-1 space-y-8">
				<div class="space-y-4">
					<div class="flex items-center gap-3">
						<div class="h-px w-12 bg-gradient-to-r from-green-600 to-transparent"></div>
						<span class="text-sm font-medium uppercase tracking-wider text-gray-500"
							>San Ramon Valley</span
						>
					</div>
					<h1
						class="font-serif text-6xl font-bold leading-tight tracking-tight text-gray-900 md:text-7xl lg:text-8xl"
					>
						Badminton
					</h1>
					<p class="max-w-xl text-lg leading-relaxed text-gray-600">
						Join our school badminton team or club. Compete at the highest level or play
						recreationally in a welcoming, beginner-friendly environment.
					</p>
				</div>

				<!-- CTA Buttons -->
				<div class="flex flex-wrap items-center gap-4">
					<a
						href="https://bluechipathletic.com/collections/san-ramon-valley-badminton"
						target="_blank"
						rel="noopener noreferrer"
						class="group relative inline-flex items-center gap-2 overflow-hidden rounded-lg border border-gray-200 bg-white px-6 py-3 text-sm font-medium text-gray-900 transition-all hover:border-green-600 hover:bg-green-50 hover:text-green-900"
					>
						<span>Merch Store</span>
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

					<a
						href="https://www.remind.com/join/YOURCODE"
						target="_blank"
						rel="noopener noreferrer"
						class="inline-flex items-center gap-2 rounded-lg border border-gray-200 bg-white px-6 py-3 text-sm font-medium text-gray-900 transition-all hover:border-green-600 hover:bg-green-50 hover:text-green-900"
					>
						Join Remind
					</a>
				</div>
			</div>

			<!-- Hero Image -->
			<div class="relative flex-1">
				<div class="absolute -inset-4 -z-10">
					<DotMatrix density="normal" pulse={true} />
				</div>
				<div
					class="aspect-square overflow-hidden rounded-2xl border border-gray-200 bg-gray-50 shadow-sm"
				>
					<img
						src="https://i.postimg.cc/0Q40JjhC/Screenshot-2025-11-11-at-02-19-08-IMG-2589-jpeg-WEBP-Image-898-1059-pixels.png"
						alt="SRV Badminton Logo"
						loading="eager"
						class="h-full w-full object-cover"
					/>
				</div>
			</div>
		</div>
	</section>

	<!-- INTEREST FORMS SECTION -->
	<section class="relative mx-auto max-w-7xl px-6 py-24">
		<!-- Racket decoration -->
		<div class="pointer-events-none absolute right-10 top-10 rotate-45 text-green-600/10">
			<BadmintonRacket class="h-32 w-32" />
		</div>

		<div class="mb-12 text-center">
			<h2 class="font-serif text-4xl font-bold text-gray-900 md:text-5xl">Get Involved</h2>
			<p class="mt-4 text-lg text-gray-600">Choose your path and join us</p>
		</div>

		<div class="grid gap-8 md:grid-cols-2">
			<!-- Team Card -->
			<a
				href="https://sites.google.com/view/srvhsbirdies/about/team-interest-form?authuser=0"
				target="_blank"
				rel="noopener noreferrer"
				class="group relative overflow-hidden rounded-2xl border border-gray-200 bg-white p-8 transition-all hover:border-green-600/20 hover:shadow-lg"
			>
				<div class="absolute right-0 top-0 h-32 w-32 -translate-y-8 translate-x-8">
					<DotMatrix density="sparse" pulse={false} />
				</div>
				<div class="relative space-y-4">
					<div
						class="flex h-12 w-12 items-center justify-center rounded-lg border border-green-600/20 bg-green-50"
					>
						<svg
							class="h-6 w-6 text-green-600"
							fill="none"
							viewBox="0 0 24 24"
							stroke="currentColor"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M13 10V3L4 14h7v7l9-11h-7z"
							/>
						</svg>
					</div>
					<h3 class="font-serif text-2xl font-bold text-gray-900">Competitive Team</h3>
					<p class="text-gray-600">
						Compete at the highest level. Represent SRV in matches against other schools and push
						your skills to the limit.
					</p>
					<div
						class="inline-flex items-center gap-2 text-sm font-medium text-green-600 transition-transform group-hover:translate-x-1"
					>
						<span>Apply Now</span>
						<svg class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M9 5l7 7-7 7"
							/>
						</svg>
					</div>
				</div>
			</a>

			<!-- Club Card -->
			<a
				href="https://sites.google.com/view/srvhsbirdies/about/club-interest-form?authuser=0"
				target="_blank"
				rel="noopener noreferrer"
				class="group relative overflow-hidden rounded-2xl border border-gray-200 bg-white p-8 transition-all hover:border-amber-600/20 hover:shadow-lg"
			>
				<div class="absolute right-0 top-0 h-32 w-32 -translate-y-8 translate-x-8">
					<DotMatrix density="sparse" pulse={false} />
				</div>
				<div class="relative space-y-4">
					<div
						class="flex h-12 w-12 items-center justify-center rounded-lg border border-amber-600/20 bg-amber-50"
					>
						<svg
							class="h-6 w-6 text-amber-600"
							fill="none"
							viewBox="0 0 24 24"
							stroke="currentColor"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z"
							/>
						</svg>
					</div>
					<h3 class="font-serif text-2xl font-bold text-gray-900">Recreational Club</h3>
					<p class="text-gray-600">
						Play for fun and fitness. Perfect for all skill levels. Make friends and enjoy the
						sport in a relaxed environment.
					</p>
					<div
						class="inline-flex items-center gap-2 text-sm font-medium text-amber-600 transition-transform group-hover:translate-x-1"
					>
						<span>Join Now</span>
						<svg class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M9 5l7 7-7 7"
							/>
						</svg>
					</div>
				</div>
			</a>
		</div>
	</section>

	<!-- BENEFITS SECTION -->
	<section class="relative mx-auto max-w-7xl px-6 py-24">
		<div class="absolute inset-0 -z-10">
			<div class="absolute inset-y-0 left-1/2 w-px bg-gradient-to-b from-transparent via-gray-200 to-transparent"></div>
		</div>

		<!-- Shuttlecock decorations -->
		<div class="pointer-events-none absolute left-4 bottom-20 -rotate-12 text-green-600/15">
			<BadmintonShuttlecock class="h-20 w-20" animate={true} />
		</div>
		<div class="pointer-events-none absolute right-8 top-32 rotate-12 text-amber-600/15">
			<BadmintonShuttlecock class="h-16 w-16" animate={true} />
		</div>

		<div class="mb-16 text-center">
			<h2 class="font-serif text-4xl font-bold text-gray-900 md:text-5xl">Why Badminton?</h2>
		</div>

		<div class="grid gap-12 md:grid-cols-2">
			<!-- Fitness -->
			<div class="group space-y-4">
				<div class="flex items-start gap-4">
					<div
						class="flex h-10 w-10 shrink-0 items-center justify-center rounded-lg border border-gray-200 bg-gray-50 transition-colors group-hover:border-green-600/20 group-hover:bg-green-50"
					>
						<span class="text-xl">💪</span>
					</div>
					<div class="space-y-2">
						<h3 class="text-xl font-semibold text-gray-900">Physical Fitness</h3>
						<p class="leading-relaxed text-gray-600">
							Build strength, agility, and endurance through fast-paced matches. Badminton engages
							your entire body, improving cardiovascular health and muscle tone.
						</p>
					</div>
				</div>
			</div>

			<!-- Community -->
			<div class="group space-y-4">
				<div class="flex items-start gap-4">
					<div
						class="flex h-10 w-10 shrink-0 items-center justify-center rounded-lg border border-gray-200 bg-gray-50 transition-colors group-hover:border-amber-600/20 group-hover:bg-amber-50"
					>
						<span class="text-xl">🤝</span>
					</div>
					<div class="space-y-2">
						<h3 class="text-xl font-semibold text-gray-900">Strong Community</h3>
						<p class="leading-relaxed text-gray-600">
							Join a supportive community of players who share your passion. Make lasting
							friendships and be part of something bigger than yourself.
						</p>
					</div>
				</div>
			</div>

			<!-- Mental Acuity -->
			<div class="group space-y-4">
				<div class="flex items-start gap-4">
					<div
						class="flex h-10 w-10 shrink-0 items-center justify-center rounded-lg border border-gray-200 bg-gray-50 transition-colors group-hover:border-green-600/20 group-hover:bg-green-50"
					>
						<span class="text-xl">🧠</span>
					</div>
					<div class="space-y-2">
						<h3 class="text-xl font-semibold text-gray-900">Strategic Thinking</h3>
						<p class="leading-relaxed text-gray-600">
							Develop quick decision-making and tactical awareness. Every match challenges your
							mind as much as your body.
						</p>
					</div>
				</div>
			</div>

			<!-- All Levels -->
			<div class="group space-y-4">
				<div class="flex items-start gap-4">
					<div
						class="flex h-10 w-10 shrink-0 items-center justify-center rounded-lg border border-gray-200 bg-gray-50 transition-colors group-hover:border-amber-600/20 group-hover:bg-amber-50"
					>
						<span class="text-xl">🎯</span>
					</div>
					<div class="space-y-2">
						<h3 class="text-xl font-semibold text-gray-900">All Skill Levels</h3>
						<p class="leading-relaxed text-gray-600">
							Whether you're a complete beginner or an experienced player, there's a place for you.
							We welcome everyone.
						</p>
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- WOLVES LOGO SECTION -->
	<section class="relative mx-auto max-w-7xl px-6 py-24">
		<div class="flex items-center justify-center">
			<div class="relative">
				<div class="absolute inset-0 -z-10 blur-2xl">
					<div
						class="h-full w-full rounded-full bg-gradient-to-br from-green-500/10 to-amber-500/10"
					></div>
				</div>
				<img
					src="https://srvhs.srvusd.net/Athletics/__ccms_cepicture_images/bc641cc4-8ada-4e82-b68b-1c8f3fd96926.JPG"
					alt="SRV Wolves Logo"
					class="h-32 w-32 object-contain opacity-80 transition-opacity duration-300 hover:opacity-100"
				/>
			</div>
		</div>
	</section>
</main>

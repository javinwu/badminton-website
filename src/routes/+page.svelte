<script lang="ts">
	import DotMatrix from '$lib/components/DotMatrix.svelte';
	import ScrollReveal from '$lib/components/ScrollReveal.svelte';
	import { onMount } from 'svelte';

	let orientation = $state(0);
	let speed = $state(0);
	let hovering = $state(false);

	const ACCELERATION = 0.05;
	const FRICTION = 0.92; // Multiplier for smooth deceleration
	const MAX_VELOCITY = 20;

	onMount(() => {
		const animation = () => {
			// Update rotation
			orientation += speed;

			// Speed up while hovering
			if (hovering && speed < MAX_VELOCITY) {
				speed += ACCELERATION;
			}
			// Slow down when not hovering (smooth deceleration)
			else if (!hovering && speed > 0) {
				speed *= FRICTION;
				// Stop completely when very slow
				if (speed < 0.01) {
					speed = 0;
				}
			}

			requestAnimationFrame(animation);
		};

		requestAnimationFrame(animation);
	});
</script>

<main class="flex-grow">
	<!-- HERO SECTION -->
	<section class="relative mx-auto max-w-7xl px-6 py-32 md:py-48">
		<!-- Decorative shuttlecocks -->
		<div class="absolute left-12 top-24 text-green-600/10">
			<svg class="h-16 w-16 rotate-12" viewBox="0 0 64 64" fill="none" xmlns="http://www.w3.org/2000/svg">
				<!-- Cork/head -->
				<circle cx="32" cy="20" r="6" fill="currentColor" />
				<!-- Feathers -->
				<path d="M32 26 L28 45 L32 42 L36 45 Z" fill="currentColor" opacity="0.6" />
				<path d="M32 26 L24 42 L28 40 L32 42 Z" fill="currentColor" opacity="0.4" />
				<path d="M32 26 L40 42 L36 40 L32 42 Z" fill="currentColor" opacity="0.4" />
			</svg>
		</div>
		<div class="absolute right-16 bottom-12 text-amber-600/10">
			<svg class="h-12 w-12 -rotate-45" viewBox="0 0 64 64" fill="none" xmlns="http://www.w3.org/2000/svg">
				<!-- Cork/head -->
				<circle cx="32" cy="20" r="6" fill="currentColor" />
				<!-- Feathers -->
				<path d="M32 26 L28 45 L32 42 L36 45 Z" fill="currentColor" opacity="0.6" />
				<path d="M32 26 L24 42 L28 40 L32 42 Z" fill="currentColor" opacity="0.4" />
				<path d="M32 26 L40 42 L36 40 L32 42 Z" fill="currentColor" opacity="0.4" />
			</svg>
		</div>

		<div class="flex flex-col items-center gap-16 md:flex-row md:items-start md:gap-24">
			<!-- Hero Text -->
			<div class="flex-1 space-y-8">
				<div class="space-y-4">
					<div class="flex items-center gap-3">
						<div class="h-px w-12 bg-gradient-to-r from-green-600 via-amber-500 to-transparent"></div>
						<span class="text-sm font-medium uppercase tracking-wider text-gray-500"
							>San Ramon Valley</span
						>
					</div>
					<h1
						class="bg-gradient-to-br from-gray-900 via-green-900 to-gray-900 bg-clip-text font-serif text-6xl font-bold leading-tight tracking-tight text-transparent md:text-7xl lg:text-8xl"
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
					class="aspect-square max-w-[450px] overflow-hidden rounded-2xl border border-gray-200 bg-gray-50 shadow-sm"
					style:rotate={`${orientation}deg`}
				>
					<img
						src="https://i.postimg.cc/0Q40JjhC/Screenshot-2025-11-11-at-02-19-08-IMG-2589-jpeg-WEBP-Image-898-1059-pixels.png"
						alt="SRV Badminton Logo"
						loading="lazy"
						class="h-full w-full object-cover"
						onmouseenter={() => (hovering = true)}
						onmouseleave={() => (hovering = false)}
					/>
				</div>
			</div>
		</div>
	</section>

	<!-- INTEREST FORMS SECTION -->
	<section class="relative mx-auto max-w-7xl px-6 py-24">
		<ScrollReveal direction="scale" duration={800} threshold={0.2}>
			<div class="mb-12 text-center">
				<h2 class="font-serif text-4xl font-bold text-gray-900 md:text-5xl">Get Involved</h2>
				<div class="mx-auto mt-4 flex w-fit items-center gap-2">
					<div class="h-px w-8 bg-gradient-to-r from-transparent via-green-600 to-transparent"></div>
					<p class="text-lg text-gray-600">Choose your path and join us</p>
					<div class="h-px w-8 bg-gradient-to-r from-transparent via-amber-500 to-transparent"></div>
				</div>
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
						class="flex h-12 w-12 items-center justify-center rounded-lg border border-green-600/20 bg-gradient-to-br from-green-50 to-green-100/50"
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
					<h3 class="bg-gradient-to-br from-gray-900 to-green-900 bg-clip-text font-serif text-2xl font-bold text-transparent">Competitive Team</h3>
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
						class="flex h-12 w-12 items-center justify-center rounded-lg border border-amber-600/20 bg-gradient-to-br from-amber-50 to-amber-100/50"
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
					<h3 class="bg-gradient-to-br from-gray-900 to-amber-900 bg-clip-text font-serif text-2xl font-bold text-transparent">Recreational Club</h3>
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
		</ScrollReveal>
	</section>

	<!-- BENEFITS SECTION -->
	<section class="relative mx-auto max-w-7xl px-6 py-24">
		<div class="absolute inset-0 -z-10">
			<div class="absolute inset-y-0 left-1/2 w-px bg-gradient-to-b from-transparent via-gray-200 to-transparent"></div>
		</div>

		<!-- Decorative racket -->
		<div class="absolute right-8 top-32 text-green-600/8">
			<svg class="h-24 w-24 rotate-45" viewBox="0 0 64 64" fill="none" xmlns="http://www.w3.org/2000/svg">
				<!-- Handle -->
				<rect x="28" y="40" width="8" height="20" rx="4" fill="currentColor" opacity="0.5" />
				<!-- Racket frame -->
				<circle cx="32" cy="24" r="14" stroke="currentColor" stroke-width="2.5" fill="none" />
				<!-- Strings -->
				<line x1="32" y1="12" x2="32" y2="36" stroke="currentColor" opacity="0.3" stroke-width="0.8" />
				<line x1="26" y1="12" x2="26" y2="36" stroke="currentColor" opacity="0.3" stroke-width="0.8" />
				<line x1="38" y1="12" x2="38" y2="36" stroke="currentColor" opacity="0.3" stroke-width="0.8" />
				<line x1="20" y1="24" x2="44" y2="24" stroke="currentColor" opacity="0.3" stroke-width="0.8" />
				<line x1="20" y1="18" x2="44" y2="18" stroke="currentColor" opacity="0.3" stroke-width="0.8" />
				<line x1="20" y1="30" x2="44" y2="30" stroke="currentColor" opacity="0.3" stroke-width="0.8" />
			</svg>
		</div>
		<div class="absolute left-12 bottom-24 text-amber-600/8">
			<svg class="h-20 w-20 -rotate-12" viewBox="0 0 64 64" fill="none" xmlns="http://www.w3.org/2000/svg">
				<!-- Handle -->
				<rect x="28" y="40" width="8" height="20" rx="4" fill="currentColor" opacity="0.5" />
				<!-- Racket frame -->
				<circle cx="32" cy="24" r="14" stroke="currentColor" stroke-width="2.5" fill="none" />
				<!-- Strings -->
				<line x1="32" y1="12" x2="32" y2="36" stroke="currentColor" opacity="0.3" stroke-width="0.8" />
				<line x1="26" y1="12" x2="26" y2="36" stroke="currentColor" opacity="0.3" stroke-width="0.8" />
				<line x1="38" y1="12" x2="38" y2="36" stroke="currentColor" opacity="0.3" stroke-width="0.8" />
				<line x1="20" y1="24" x2="44" y2="24" stroke="currentColor" opacity="0.3" stroke-width="0.8" />
				<line x1="20" y1="18" x2="44" y2="18" stroke="currentColor" opacity="0.3" stroke-width="0.8" />
				<line x1="20" y1="30" x2="44" y2="30" stroke="currentColor" opacity="0.3" stroke-width="0.8" />
			</svg>
		</div>

		<ScrollReveal direction="scale" duration={800} threshold={0.2}>
			<div class="mb-16 text-center">
				<h2 class="font-serif text-4xl font-bold text-gray-900 md:text-5xl">Why Badminton?</h2>
				<div class="mx-auto mt-3 h-1 w-24 rounded-full bg-gradient-to-r from-green-600 to-amber-500"></div>
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
		</ScrollReveal>
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
					class="h-32 w-32 object-contain"
				/>
			</div>
		</div>
	</section>
</main>

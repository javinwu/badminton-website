<script lang="ts">
	import ScrollReveal from '$lib/components/ScrollReveal.svelte';
</script>

<main class="flex-grow">
	<!-- HERO (no animation - already visible on load) -->
	<section
		id="hero"
		class="flex min-h-screen flex-col items-center justify-center gap-16 px-8 pt-24 md:flex-row md:px-32"
	>
		<div
			id="hero-text"
			class="flex flex-col justify-center gap-4 text-left transition-all duration-700 md:w-1/2"
		>
			<h1
				class="text-5xl font-bold tracking-tight text-[#006400] uppercase select-none sm:text-6xl md:text-7xl"
			>
				SRV
			</h1>
			<h2 class="mb-6 text-3xl font-semibold tracking-wide text-[#FFD700] sm:text-4xl md:text-5xl">
				𝚋𝚊𝚍𝚖𝚒𝚗𝚝𝚘𝚗
			</h2>
			<p class="text-base leading-relaxed text-[#004d00] sm:text-lg">
				join our school badminton team or club, make friends and/or compete in a competitive and
				beginner friendly environment!
			</p>

			<div class="mt-3 flex flex-wrap items-center gap-4">
				<!--Merch/Remind/Instagram -->
				<a
					href="https://bluechipathletic.com/collections/san-ramon-valley-badminton"
					target="_blank"
					class="shine-box w-fit rounded-full bg-[#FFD700] px-5 py-2 font-semibold text-[#006400] shadow-lg transition-all duration-300 hover:bg-[#e6c200]"
				>
					merch store
				</a>

				<a
					href="https://www.remind.com/join/YOURCODE"
					target="_blank"
					class="shine-box w-fit rounded-full bg-[#006400] px-5 py-2 font-semibold text-[#FFD700] shadow-lg transition-all duration-300 hover:bg-[#228B22]"
				>
					join remind
				</a>

				<a
					href="https://www.instagram.com/srvhsbadminton/"
					target="_blank"
					class="shine-box flex w-fit items-center gap-2 rounded-full bg-[#FFD700] px-5 py-2 font-semibold text-[#006400] shadow-lg transition-all duration-300 hover:bg-[#e6c200]"
				>
					<img
						src="https://cdn-icons-png.flaticon.com/512/174/174855.png"
						alt="Instagram"
						class="h-5 w-5"
					/>
					instagram
				</a>
			</div>

			<!-- Interest Forms under Merch -->
			<div id="hero-forms" class="mt-6 flex flex-col gap-6 transition-all duration-700 md:flex-row">
				<a
					id="team-box"
					href="https://sites.google.com/view/srvhsbirdies/about/team-interest-form?authuser=0"
					target="_blank"
					class="shine-box flex w-full flex-col items-center gap-3 rounded-2xl bg-[#006400] p-6 text-center shadow-xl transition-all duration-700 hover:scale-105 hover:bg-[#228B22] hover:shadow-2xl md:w-[18rem]"
				>
					<h3 class="text-2xl font-bold text-[#FFD700]">team interest form</h3>
					<p class="text-md leading-snug text-white">
						sign up! compete competitively for the school team against other schools!
					</p>
				</a>

				<a
					id="club-box"
					href="https://sites.google.com/view/srvhsbirdies/about/club-interest-form?authuser=0"
					target="_blank"
					class="shine-box flex w-full flex-col items-center gap-3 rounded-2xl bg-[#FFD700] p-6 text-center shadow-xl transition-all duration-700 hover:scale-105 hover:bg-[#e6c200] hover:shadow-2xl md:w-[18rem]"
				>
					<h3 class="text-2xl font-bold text-[#006400]">club interest form</h3>
					<p class="text-md leading-snug text-[#004d00]">
						for everyone — badminton is fun for everyone recreationally! bring your friends!
					</p>
				</a>
			</div>
		</div>

		<!-- Hero Logo -->
		<div id="hero-logo" class="flex justify-center transition-all duration-700 md:w-1/2">
			<div class="h-80 w-80 overflow-hidden rounded-xl bg-gray-200 shadow-lg md:h-96 md:w-96">
				<img
					src="https://i.postimg.cc/0Q40JjhC/Screenshot-2025-11-11-at-02-19-08-IMG-2589-jpeg-WEBP-Image-898-1059-pixels.png"
					alt="srv badminton logo"
					loading="lazy"
					class="h-full w-full object-cover"
				/>
			</div>
		</div>
	</section>

	<!-- Spacer Section with fade animation -->
	<ScrollReveal direction="fade" duration={800}>
		<section
			class="flex min-h-[30vh] flex-col items-center justify-center bg-gradient-to-b from-green-100 to-green-50 px-8 py-20 text-center"
		>
			<h2 class="mb-4 text-4xl font-semibold tracking-wide text-[#006400]">discover more ↓</h2>
			<p class="max-w-2xl text-lg leading-relaxed text-[#004d00]">
				from our welcoming club to our competitive team opportunities.
			</p>
		</section>
	</ScrollReveal>

	<!-- WHAT WE OFFER -->
	<section
		id="what-we-offer"
		class="mt-[100px] mb-64 flex min-h-[600px] flex-col items-center px-8 pb-10 md:px-32"
	>
		<!-- Heading slides up -->
		<ScrollReveal direction="up" duration={700}>
			<div class="shine-box mb-12 w-full max-w-2xl rounded-2xl bg-white p-8 text-center shadow-xl">
				<h2 class="mb-2 text-4xl font-bold text-[#006400]">what badminton can help with</h2>
			</div>
		</ScrollReveal>

		<!-- Cards slide in from left and right with stagger -->
		<div class="flex w-full max-w-4xl flex-col gap-8 md:flex-row">
			<ScrollReveal direction="left" duration={700} delay={100}>
				<div
					class="shine-box relative flex-1 overflow-hidden rounded-2xl bg-white p-8 text-center shadow-xl"
				>
					<div
						class="absolute inset-0 bg-cover bg-center opacity-20"
						style="background-image: url('https://images.unsplash.com/photo-1626224583764-f87db24ac4ea?w=800');"
					></div>
					<div class="relative z-10">
						<h3 class="mb-4 text-3xl font-bold text-[#006400]">a way to stay fit</h3>
						<p class="text-lg leading-relaxed text-[#004d00]">
							badminton builds muscles such as your leg and arm muscles, helping you stay fit and
							strong through fast-paced matches.
						</p>
					</div>
				</div>
			</ScrollReveal>

			<ScrollReveal direction="right" duration={700} delay={200}>
				<div
					class="shine-box relative flex-1 overflow-hidden rounded-2xl bg-white p-8 text-center shadow-xl"
				>
					<div
						class="absolute inset-0 bg-cover bg-center opacity-20"
						style="background-image: url('https://www.infront.sport/hubfs/Imported_Blog_Media/BWF_and_Yonex_seal-2-1.webp');"
					></div>
					<div class="relative z-10">
						<h3 class="mb-4 text-3xl font-bold text-[#FFD700]">community</h3>
						<p class="text-lg leading-relaxed text-[#004d00]">
							a place to make friends, have fun, and be part of a supportive community that loves
							badminton as much as you do.
						</p>
					</div>
				</div>
			</ScrollReveal>
		</div>
	</section>
</main>

<!-- SRV WOLVES LOGO ABOVE FOOTER - scale animation -->
<div class="min-h-[300px]">
	<ScrollReveal direction="scale" duration={600} rootMargin="0px 0px -20px 0px">
		<div class="flex w-full justify-center bg-green-50 py-6">
			<img
				src="https://srvhs.srvusd.net/Athletics/__ccms_cepicture_images/bc641cc4-8ada-4e82-b68b-1c8f3fd96926.JPG"
				alt="SRV Wolves Logo"
				class="h-32 w-32 object-contain opacity-90 transition duration-300 hover:opacity-100"
			/>
		</div>
	</ScrollReveal>
</div>

<style>
	/* Shine animation for glowing boxes */
	@keyframes shine {
		0% {
			box-shadow:
				0 0 12px rgba(255, 215, 0, 0.3),
				0 0 0 rgba(0, 100, 0, 0);
		}
		50% {
			box-shadow:
				0 0 26px rgba(255, 215, 0, 0.7),
				0 0 40px rgba(0, 100, 0, 0.4);
		}
		100% {
			box-shadow:
				0 0 12px rgba(255, 215, 0, 0.3),
				0 0 0 rgba(0, 100, 0, 0);
		}
	}

	.shine-box {
		animation: shine 2s infinite ease-in-out;
	}

	/* Team/Club hover pop-out effect */
	#team-box,
	#club-box {
		transition:
			transform 0.3s ease,
			box-shadow 0.3s ease;
		cursor: pointer;
	}

	#team-box:hover,
	#club-box:hover {
		transform: scale(1.08);
		box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
	}

	/* Smooth text pop inside cards */
	#team-box h3,
	#club-box h3,
	#team-box p,
	#club-box p {
		transition: transform 0.3s ease;
	}

	#team-box:hover h3,
	#club-box:hover h3,
	#team-box:hover p,
	#club-box:hover p {
		transform: scale(1.05);
	}

	/* Responsive hero-form buttons */
	#hero-forms a {
		flex: 1;
		min-width: 14rem;
	}
</style>

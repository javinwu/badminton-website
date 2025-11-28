<script lang="ts">
	// const image = document.getElementById("hero-image");
	// let orientation = 0;
	// const ACCELERATION = 0.05;
	// const FRICTION = -0.07;
	// const MAX_VELOCITY = 20;
	// let speed = 0;

	// let hovering = false;
	
	// const animation = () => {
	// 	orientation += speed;
	// 	if (hovering) {
	// 		if (speed <= MAX_VELOCITY) {
	// 			speed += ACCELERATION;
	// 		}
	// 	} else if (speed > 0) {
	// 		speed += FRICTION;
	// 	} else if (speed < 0) {https://prettier.io/docs/plugins
	// 		speed = 0;
	// 	}
	// 	image!.style.rotate = `${orientation}deg`;
	// 	requestAnimationFrame(animation);
	// }

	// requestAnimationFrame(animation);

	// image.addEventListener("mouseenter", () => {
	// 	hovering = true;
	// })

	// image.addEventListener("mouseleave", () => {
	// 	hovering = false;
	// })
</script>



	<body class="bg-green-50 font-sans overflow-x-hidden relative lowercase">
		<!--Nav Bar -->
		<nav
			class="fixed top-0 left-0 w-full bg-[#006400] text-[#FFD700] shadow-md z-50"
		>
			<div
				class="max-w-7xl mx-auto px-6 py-3 flex justify-between items-center"
			>
				<a
					href="/gallery"
					class="px-4 py-1 rounded-full bg-[#FFD700] text-[#006400] font-semibold hover:bg-white transition shadow-md"
				>
					gallery
				</a>
			</div>
		</nav>
	</body>

	<!-- NAVBAR SPACER (keeps content from hiding behind navbar) -->
	<div class="h-[70px]"></div>

	<main class="flex-grow">
		<!-- LOGO HEADER -->
		<header
			class="flex items-center justify-center py-4 bg-transparent fixed top-0 left-0 w-full z-50 pointer-events-none"
		>
			<a
				href="/"
				class="hover:opacity-80 hover:scale-110 transition-transform duration-300 pointer-events-auto"
			>
				<img
					src="https://image.maxpreps.io/school-mascot/5/9/4/594e7f5d-3e25-480c-bc2c-c15cbf09c737.gif"
					alt="srv wolves logo"
					class="logo w-20 h-20 rounded-full shadow-lg border-2 border-[#FFD700]"
				/>
			</a>
		</header>

		<!-- MADE BY JAVIN W -->
		<div
			id="made-by"
			class="fixed top-4 right-4 text-[#006400] text-sm font-medium tracking-wide z-50"
		>
			made by javin w
		</div>

		<!-- HERO -->
		<section
			id="hero"
			class="flex flex-col md:flex-row items-center justify-center min-h-screen px-8 md:px-32 gap-16 pt-24"
		>
			<div
				id="hero-text"
				class="flex flex-col justify-center md:w-1/2 text-left gap-4 transition-all duration-700"
			>
				<h1
					class="text-5xl sm:text-6xl md:text-7xl font-bold text-[#006400] select-none tracking-tight uppercase"
				>
					SRV
				</h1>
				<h2
					class="text-3xl sm:text-4xl md:text-5xl font-semibold text-[#FFD700] tracking-wide mb-6"
				>
					𝚋𝚊𝚍𝚖𝚒𝚗𝚝𝚘𝚗
				</h2>
				<p class="text-base sm:text-lg text-[#004d00] leading-relaxed">
					join our school badminton team or club, make friends and/or
					compete in a competitive and beginner friendly environment!
				</p>

				<div class="flex flex-wrap items-center gap-4 mt-3">
					<!--Merch/Remind/Instagram -->
					<a
						href="https://bluechipathletic.com/collections/san-ramon-valley-badminton"
						target="_blank"
						class="bg-[#FFD700] text-[#006400] px-5 py-2 rounded-full font-semibold shadow-lg hover:bg-[#e6c200] transition-all duration-300 shine-box w-fit"
					>
						merch store
					</a>

					<a
						href="https://www.remind.com/join/YOURCODE"
						target="_blank"
						class="bg-[#006400] text-[#FFD700] px-5 py-2 rounded-full font-semibold shadow-lg hover:bg-[#228B22] transition-all duration-300 shine-box w-fit"
					>
						join remind
					</a>

					<a
						href="https://www.instagram.com/srvhsbadminton/"
						target="_blank"
						class="bg-[#FFD700] text-[#006400] px-5 py-2 rounded-full font-semibold shadow-lg hover:bg-[#e6c200] transition-all duration-300 shine-box w-fit flex items-center gap-2"
					>
						<img
							src="https://cdn-icons-png.flaticon.com/512/174/174855.png"
							class="w-5 h-5"
						/>
						instagram
					</a>
				</div>

				<!-- Interest Forms under Merch -->
				<div
					id="hero-forms"
					class="flex flex-col md:flex-row gap-6 mt-6 transition-all duration-700"
				>
					<a
						id="team-box"
						href="https://sites.google.com/view/srvhsbirdies/about/team-interest-form?authuser=0"
						target="_blank"
						class="shine-box bg-[#006400] text-center rounded-2xl shadow-xl hover:bg-[#228B22] transition-all duration-700 w-full md:w-[18rem] p-6 flex flex-col items-center gap-3 hover:scale-105 hover:shadow-2xl"
					>
						<h3 class="text-2xl font-bold text-[#FFD700]">
							team interest form
						</h3>
						<p class="text-md text-white leading-snug">
							sign up! compete competitively for the school team
							against other schools!
						</p>
					</a>

					<a
						id="club-box"
						href="https://sites.google.com/view/srvhsbirdies/about/club-interest-form?authuser=0"
						target="_blank"
						class="shine-box bg-[#FFD700] text-center rounded-2xl shadow-xl hover:bg-[#e6c200] transition-all duration-700 w-full md:w-[18rem] p-6 flex flex-col items-center gap-3 hover:scale-105 hover:shadow-2xl"
					>
						<h3 class="text-2xl font-bold text-[#006400]">
							club interest form
						</h3>
						<p class="text-md text-[#004d00] leading-snug">
							for everyone — badminton is fun for everyone
							recreationally! bring your friends!
						</p>
					</a>
				</div>
			</div>

			<!-- Hero Logo -->
			<div
				id="hero-logo"
				class="md:w-1/2 flex justify-center transition-all duration-700"
			>
				<div
					class="w-80 h-80 md:w-96 md:h-96 bg-gray-200 rounded-xl shadow-lg overflow-hidden"
					id="hero-image"

				>
					<img
						src="https://i.postimg.cc/0Q40JjhC/Screenshot-2025-11-11-at-02-19-08-IMG-2589-jpeg-WEBP-Image-898-1059-pixels.png"
						alt="srv badminton logo"	
						loading="lazy"
						class="w-full h-full object-cover"
					/>
				</div>
			</div>
		</section>

		<!-- Spacer Section -->
		<section
			class="min-h-[30vh] flex flex-col items-center justify-center text-center bg-gradient-to-b from-green-100 to-green-50 px-8 py-20"
		>
			<h2
				class="text-4xl font-semibold mb-4 text-[#006400] tracking-wide"
			>
				discover more ↓
			</h2>
			<p class="text-lg text-[#004d00] max-w-2xl leading-relaxed">
				from our welcoming club to our competitive team opportunities.
			</p>
		</section>

		<!-- WHAT WE OFFER -->
		<section
			id="what-we-offer"
			class="flex flex-col items-center px-8 md:px-32 mt-[100px] mb-64 pb-10 transition-all duration-700 opacity-0 translate-y-10"
		>
			<div
				class="shine-box bg-white text-center rounded-2xl shadow-xl w-full max-w-2xl p-8 mb-12"
			>
				<h2 class="text-4xl font-bold text-[#006400] mb-2">
					what badminton can help with
				</h2>
			</div>

			<div class="flex flex-col md:flex-row gap-8 w-full max-w-4xl">
				<div
					class="shine-box bg-white text-center rounded-2xl shadow-xl flex-1 p-8 relative overflow-hidden"
				>
					<div
						class="absolute inset-0 opacity-20 bg-cover bg-center"
						style="background-image: url('https://images.unsplash.com/photo-1626224583764-f87db24ac4ea?w=800');"
					>
					</div>
					<div class="relative z-10">
						<h3 class="text-3xl font-bold text-[#006400] mb-4">
							a way to stay fit
						</h3>
						<p class="text-lg text-[#004d00] leading-relaxed">
							badminton builds muscles such as your leg and arm
							muscles, helping you stay fit and strong through
							fast-paced matches.
						</p>
					</div>
				</div>

				<div
					class="shine-box bg-white text-center rounded-2xl shadow-xl flex-1 p-8 relative overflow-hidden"
				>
					<div
						class="absolute inset-0 opacity-20 bg-cover bg-center"
						style="background-image: url('https://www.infront.sport/hubfs/Imported_Blog_Media/BWF_and_Yonex_seal-2-1.webp');"
					>
					</div>
					<div class="relative z-10">
						<h3 class="text-3xl font-bold text-[#FFD700] mb-4">
							community
						</h3>
						<p class="text-lg text-[#004d00] leading-relaxed">
							a place to make friends, have fun, and be part of a
							supportive community that loves badminton as much as
							you do.
						</p>
					</div>
				</div>
			</div>
		</section>
	</main>
	<!-- SRV WOLVES LOGO ABOVE FOOTER -->
	<div class="w-full flex justify-center bg-green-50 py-6">
		<img
			src="https://srvhs.srvusd.net/Athletics/__ccms_cepicture_images/bc641cc4-8ada-4e82-b68b-1c8f3fd96926.JPG"
			alt="SRV Wolves Logo"
			class="w-32 h-32 object-contain opacity-90 hover:opacity-100 transition duration-300"
		/>
	</div>

	<!-- Footer -->
	<footer
		id="footer"
		class="bg-[#006400] text-[#FFD700] text-center py-6 opacity-0 translate-y-10 transition-all duration-1000 mt-auto"
	>
		<p class="text-sm tracking-wide">
			© 2025 san ramon valley badminton • all rights reserved
		</p>
	</footer>

<style>
        /* --------------------------------------------------
   Sparkle animation for merch button
-------------------------------------------------- */
@keyframes sparkle {
  0%, 100% {
    box-shadow: 0 0 6px #FFD700, 0 0 14px #FFD700;
  }
  50% {
    box-shadow: 0 0 18px #FFD700, 0 0 28px #FFD700;
  }
}

.sparkle-button {
  animation: sparkle 1.5s ease-in-out infinite alternate;
}

/* --------------------------------------------------
   Shine animation for glowing boxes
-------------------------------------------------- */
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

/* --------------------------------------------------
   Smooth slide-in animations
-------------------------------------------------- */
.slide-in-left,
.slide-in-right {
  opacity: 0;
  transition: opacity 1s cubic-bezier(0.22, 1, 0.36, 1),
              transform 1s cubic-bezier(0.22, 1, 0.36, 1);
}

.slide-in-left {
  transform: translateX(-140px);
}

.slide-in-right {
  transform: translateX(140px);
}

.visible {
  opacity: 1 !important;
  transform: translateX(0) !important;
}

/* --------------------------------------------------
   Footer fade + slide-up
-------------------------------------------------- */
#footer {
  opacity: 0;
  transform: translateY(40px);
  transition: opacity 1s ease-in-out, transform 1s ease-in-out;
}

#footer.visible {
  opacity: 1;
  transform: translateY(0);
}

/* --------------------------------------------------
   Bounce slam animation for buttons
-------------------------------------------------- */
@keyframes bounce-slam {
  0%   { transform: scale(1); }
  50%  { transform: scale(1.2); }
  70%  { transform: scale(0.9); }
  100% { transform: scale(1); }
}

.bounce {
  animation: bounce-slam 0.6s ease-out forwards;
}

/* --------------------------------------------------
   Team/Club hover pop-out effect
-------------------------------------------------- */
#team-box,
#club-box {
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  cursor: pointer;
}

#team-box:hover,
#club-box:hover {
  transform: scale(1.08);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
}

/* smooth text pop inside cards */
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

/* --------------------------------------------------
   Responsive hero-form buttons
-------------------------------------------------- */
#hero-forms a {
  flex: 1;
  min-width: 14rem;
}

/*back ground*/

#discover-more {
  background-color: #d0f0c0; /* Light green similar to original background */
  transition: background-color 1s ease;
}

#discover-more.visible {
  background-color: #ffffff; /* Fade to white when visible */
}
</style>
<script lang="ts">
	import DotMatrix from '$lib/components/DotMatrix.svelte';
	import birdie from '$lib/assets/badminton-birdie.svg';
	import racket from '$lib/assets/racket.svg';

	// ====================================
	// EASY PHOTO MANAGEMENT
	// Just paste image URLs here!
	// ====================================

	// Club photos - paste URLs in this array
	const clubPhotos = [
		'https://scontent-sjc6-1.cdninstagram.com/v/t51.82787-15/527370875_18048247631629344_2885519947006656866_n.jpg?stp=dst-jpg_e35_s1080x1080_tt6&_nc_cat=108&ig_cache_key=MzY4OTEzMjcwOTk5MTM3OTU2OA%3D%3D.3-ccb7-5&ccb=7-5&_nc_sid=58cdad&efg=eyJ2ZW5jb2RlX3RhZyI6InhwaWRzLjE0NDB4MTA4MC5zZHIuQzMifQ%3D%3D&_nc_ohc=v2nW8I7Q85IQ7kNvwGIJJQh&_nc_oc=AdlCg0jO2WljCDKMyx7LotQqm9lwuBXVPIlETRkl3UJCYGk3laqQ2ldbA5KPMkWIDjY&_nc_ad=z-m&_nc_cid=0&_nc_zt=23&_nc_ht=scontent-sjc6-1.cdninstagram.com&_nc_gid=_AhDw5o_3WeMprdLsDXGdA&oh=00_Afj_ikrsR2zdUU0lNvXO19ULlbbE8UfCYUw5yfDCu2CZNQ&oe=692AB0CB',
		'https://scontent-sjc3-1.cdninstagram.com/v/t51.82787-15/527187002_18048247505629344_7559480198226464052_n.jpg?stp=dst-jpg_e35_s1080x1080_tt6&_nc_cat=110&ig_cache_key=MzY4OTEzMjcwOTk5MTE2MzU2OQ%3D%3D.3-ccb7-5&ccb=7-5&_nc_sid=58cdad&efg=eyJ2ZW5jb2RlX3RhZyI6InhwaWRzLjE0NDB4MTA4MC5zZHIuQzMifQ%3D%3D&_nc_ohc=G2jfq6AxpA8Q7kNvwGRLAVc&_nc_oc=AdlS1_VTc9sxaN2AZ3IYvhNt4RmPy5SJVpRSO-1_YxTabAC0pDo85FCPqvUkDvqo5ag&_nc_ad=z-m&_nc_cid=0&_nc_zt=23&_nc_ht=scontent-sjc3-1.cdninstagram.com&_nc_gid=_AhDw5o_3WeMprdLsDXGdA&oh=00_AfjwRGFS7lwlzJHJv1j_Huq6BPPXsc4Nd28oscQI_B9idA&oe=692AA296',
		'https://scontent-sjc3-1.cdninstagram.com/v/t51.82787-15/526736677_18048247559629344_2443057698005207092_n.jpg?stp=dst-jpg_e35_s1080x1080_tt6&_nc_cat=110&ig_cache_key=MzY4OTEzMjcxMDI2ODIwNTM2Ng%3D%3D.3-ccb7-5&ccb=7-5&_nc_sid=58cdad&efg=eyJ2ZW5jb2RlX3RhZyI6InhwaWRzLjE0NDB4MTA4MC5zZHIuQzMifQ%3D%3D&_nc_ohc=W1-CWGqSh5cQ7kNvwEwaQh-&_nc_oc=AdlT0SlJBDvu3jkVys1R1cKlYN5U-g13qDLMawqLnzRk-oSIBnA8B8t4ddtxEs38HKY&_nc_ad=z-m&_nc_cid=0&_nc_zt=23&_nc_ht=scontent-sjc3-1.cdninstagram.com&_nc_gid=_AhDw5o_3WeMprdLsDXGdA&oh=00_Afiq6nbMgWkx81vfSv2bMmw1fUUbvRrQPNT34qMwUsWFiQ&oe=692A9616'
		// Add more club photo URLs here...
	];

	// Team photos - paste URLs in this array
	const teamPhotos = [
		// Add team photo URLs here...
		
	];

	let selectedImage = $state<string | null>(null);

	function openModal(src: string) {
		selectedImage = src;
	}

	function closeModal() {
		selectedImage = null;
	}
</script>

<svelte:head>
	<title>Gallery — SRV Badminton</title>
</svelte:head>

<main class="flex-grow">
	<!-- HERO SECTION -->
	<section class="relative mx-auto max-w-7x1 px-12 py-32 md:py-40">
		<!-- Decorative elements -->
		<img src={birdie} alt="" class="absolute left-8 top-16 h-14 w-14 rotate-45 opacity-[0.06] brightness-0" />
		<img src={birdie} alt="" class="absolute right-12 top-20 h-12 w-12 -rotate-12 opacity-[0.06] brightness-0 saturate-[0.8] hue-rotate-[45deg]" />
		<img src={racket} alt="" class="absolute left-16 bottom-32 h-16 w-16 rotate-[30deg] opacity-[0.04] brightness-0" />

		<div class="text-center">
			<div class="mb-6 flex items-center justify-center gap-3">
				<div class="h-px w-12 bg-gradient-to-r from-transparent via-green-600 to-amber-500"></div>
				<span class="text-sm font-medium uppercase tracking-wider text-gray-500">Memories</span>
				<div class="h-px w-12 bg-gradient-to-r from-amber-500 via-green-600 to-transparent"></div>
			</div>
			<h1
				class="bg-gradient-to-br from-gray-900 via-green-900 to-gray-900 bg-clip-text font-serif text-5xl font-bold leading-tight tracking-tight text-transparent md:text-6xl lg:text-7xl"
			>
				Gallery
			</h1>
			<p class="mx-auto mt-6 max-w-2xl text-lg leading-relaxed text-gray-600">
				Photos from team practices, matches, and club events. Capturing the moments that make our
				badminton community special.
			</p>
		</div>
	</section>

	<!-- CLUB PHOTOS SECTION -->
	{#if clubPhotos.length > 0}
		<section class="relative mx-auto max-w-7xl px-6 py-16">
			<div class="mb-12">
				<h2 class="font-serif text-3xl font-bold text-gray-900 md:text-4xl">Club Events</h2>
				<div class="mt-3 h-1 w-20 rounded-full bg-gradient-to-r from-amber-500 to-amber-600"></div>
			</div>

			<div class="grid gap-6 sm:grid-cols-2 lg:grid-cols-3">
				{#each clubPhotos as photo, index (photo)}
					<button
						onclick={() => openModal(photo)}
						class="group relative overflow-hidden rounded-2xl border border-gray-200 bg-white shadow-sm transition-all hover:border-amber-600/20 hover:shadow-lg"
					>
						<div class="absolute right-0 top-0 h-24 w-24 -translate-y-6 translate-x-6 opacity-0 transition-opacity group-hover:opacity-100">
							<DotMatrix density="sparse" pulse={false} />
						</div>
						<img
							src={photo}
							alt="Club event photo {index + 1}"
							class="relative z-10 h-full w-full object-contain transition-transform duration-300 group-hover:scale-105"
							loading="lazy"
						/>
					</button>
				{/each}
			</div>
		</section>
	{/if}

	<!-- TEAM PHOTOS SECTION -->
	{#if teamPhotos.length > 0}
		<section class="relative mx-auto max-w-7xl px-6 py-16">
			<div class="mb-12">
				<h2 class="font-serif text-3xl font-bold text-gray-900 md:text-4xl">Team Matches</h2>
				<div class="mt-3 h-1 w-20 rounded-full bg-gradient-to-r from-green-600 to-green-700"></div>
			</div>

			<div class="grid gap-6 sm:grid-cols-2 lg:grid-cols-3">
				{#each teamPhotos as photo, index (photo)}
					<button
						onclick={() => openModal(photo)}
						class="group relative aspect-square overflow-hidden rounded-2xl border border-gray-200 bg-white shadow-sm transition-all hover:border-green-600/20 hover:shadow-lg"
					>
						<div class="absolute right-0 top-0 h-24 w-24 -translate-y-6 translate-x-6 opacity-0 transition-opacity group-hover:opacity-100">
							<DotMatrix density="sparse" pulse={false} />
						</div>
						<img
							src={photo}
							alt="Team match photo {index + 1}"
							class="relative z-10 h-full w-full object-contain transition-transform duration-300 group-hover:scale-105"
							loading="lazy"
						/>
					</button>
				{/each}
			</div>
		</section>
	{/if}

	<!-- EMPTY STATE -->
	{#if clubPhotos.length === 0 && teamPhotos.length === 0}
		<section class="relative mx-auto max-w-7xl px-6 py-24">
			<div class="flex flex-col items-center justify-center gap-6 rounded-2xl border-2 border-dashed border-gray-200 bg-gray-50 py-20 text-center">
				<div class="flex h-16 w-16 items-center justify-center rounded-full border border-gray-200 bg-white">
					<svg
						class="h-8 w-8 text-gray-400"
						fill="none"
						viewBox="0 0 24 24"
						stroke="currentColor"
					>
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M4 16l4.586-4.586a2 2 0 012.828 0L16 16m-2-2l1.586-1.586a2 2 0 012.828 0L20 14m-6-6h.01M6 20h12a2 2 0 002-2V6a2 2 0 00-2-2H6a2 2 0 00-2 2v12a2 2 0 002 2z"
						/>
					</svg>
				</div>
				<div class="space-y-2">
					<h3 class="text-xl font-semibold text-gray-900">No photos yet</h3>
					<p class="text-gray-600">Photos from our events will be posted here soon!</p>
				</div>
			</div>
		</section>
	{/if}
</main>

<!-- IMAGE MODAL -->
{#if selectedImage}
	<button
		onclick={closeModal}
		class="fixed inset-0 z-50 flex items-center justify-center bg-black/80 backdrop-blur-sm p-4"
	>
		<div class="relative max-h-[90vh] max-w-[90vw]">
			<img
				src={selectedImage}
				alt="Gallery preview"
				class="max-h-[90vh] max-w-full rounded-2xl shadow-2xl"
			/>
			<!-- Close button -->
			<div
				class="absolute right-4 top-4 flex h-10 w-10 items-center justify-center rounded-full bg-white/10 backdrop-blur-md transition-colors hover:bg-white/20"
			>
				<svg class="h-6 w-6 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor">
					<path
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="2"
						d="M6 18L18 6M6 6l12 12"
					/>
				</svg>
			</div>
		</div>
	</button>
{/if}

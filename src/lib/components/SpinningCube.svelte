<script lang="ts">
	import { onMount } from 'svelte';
	import * as THREE from 'three';
	import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls.js';

	let container: HTMLDivElement;
	let isInteracting = $state(false);
	let autoRotateSpeed = $state(0.5);

	onMount(() => {
		// Scene setup
		const scene = new THREE.Scene();
		const camera = new THREE.PerspectiveCamera(50, 1, 0.1, 1000);
		const renderer = new THREE.WebGLRenderer({ alpha: true, antialias: true });

		renderer.setSize(450, 450);
		renderer.setClearColor(0x000000, 0);
		container.appendChild(renderer.domElement);

		// Create cube geometry
		const geometry = new THREE.BoxGeometry(2, 2, 2);

		// Load texture
		const textureLoader = new THREE.TextureLoader();
		const texture = textureLoader.load(
			'https://i.postimg.cc/0Q40JjhC/Screenshot-2025-11-11-at-02-19-08-IMG-2589-jpeg-WEBP-Image-898-1059-pixels.png'
		);

		// Apply texture to all faces
		const materials = [
			new THREE.MeshBasicMaterial({ map: texture }),
			new THREE.MeshBasicMaterial({ map: texture }),
			new THREE.MeshBasicMaterial({ map: texture }),
			new THREE.MeshBasicMaterial({ map: texture }),
			new THREE.MeshBasicMaterial({ map: texture }),
			new THREE.MeshBasicMaterial({ map: texture })
		];

		const cube = new THREE.Mesh(geometry, materials);
		scene.add(cube);

		// Add edge geometry for better definition
		const edges = new THREE.EdgesGeometry(geometry);
		const lineMaterial = new THREE.LineBasicMaterial({ color: 0x000000, opacity: 0.1, transparent: true });
		const lineSegments = new THREE.LineSegments(edges, lineMaterial);
		cube.add(lineSegments);

		camera.position.z = 4;

		// Add OrbitControls for dragging
		const controls = new OrbitControls(camera, renderer.domElement);
		controls.enableDamping = true;
		controls.dampingFactor = 0.05;
		controls.enableZoom = false;
		controls.enablePan = false;

		// Detect when user is interacting
		controls.addEventListener('start', () => {
			isInteracting = true;
		});
		controls.addEventListener('end', () => {
			isInteracting = false;
		});

		// Animation loop
		const animate = () => {
			requestAnimationFrame(animate);

			// Auto-rotate when not interacting
			if (!isInteracting) {
				cube.rotation.x += autoRotateSpeed * 0.01;
				cube.rotation.y += autoRotateSpeed * 0.01;
			}

			controls.update();
			renderer.render(scene, camera);
		};

		animate();

		// Cleanup
		return () => {
			controls.dispose();
			renderer.dispose();
			geometry.dispose();
			edges.dispose();
			lineMaterial.dispose();
			materials.forEach(m => m.dispose());
			texture.dispose();
			if (container.contains(renderer.domElement)) {
				container.removeChild(renderer.domElement);
			}
		};
	});
</script>

<div
	bind:this={container}
	class="aspect-square max-w-[450px] cursor-grab active:cursor-grabbing"
></div>

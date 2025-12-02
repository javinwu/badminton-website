<script lang="ts">
	import { onMount } from 'svelte';
	import * as THREE from 'three';

	let container: HTMLDivElement;
	let isInteracting = $state(false);
	let autoRotateSpeed = $state(0.5);

	let isDragging = false;
	let previousMousePosition = { x: 0, y: 0 };

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

		// Custom mouse controls for unlimited cube rotation
		const onMouseDown = (event: MouseEvent) => {
			isDragging = true;
			isInteracting = true;
			previousMousePosition = {
				x: event.clientX,
				y: event.clientY
			};
		};

		const onMouseMove = (event: MouseEvent) => {
			if (!isDragging) return;

			const deltaX = event.clientX - previousMousePosition.x;
			const deltaY = event.clientY - previousMousePosition.y;

			// Rotate cube directly - NO BOUNDARIES
			cube.rotation.y += deltaX * 0.01;
			cube.rotation.x += deltaY * 0.01;

			previousMousePosition = {
				x: event.clientX,
				y: event.clientY
			};
		};

		const onMouseUp = () => {
			isDragging = false;
			isInteracting = false;
		};

		renderer.domElement.addEventListener('mousedown', onMouseDown);
		window.addEventListener('mousemove', onMouseMove);
		window.addEventListener('mouseup', onMouseUp);

		// Animation loop
		const animate = () => {
			requestAnimationFrame(animate);

			// Auto-rotate when not interacting
			if (!isInteracting) {
				cube.rotation.x += autoRotateSpeed * 0.01;
				cube.rotation.y += autoRotateSpeed * 0.01;
			}

			renderer.render(scene, camera);
		};

		animate();

		// Cleanup
		return () => {
			renderer.domElement.removeEventListener('mousedown', onMouseDown);
			window.removeEventListener('mousemove', onMouseMove);
			window.removeEventListener('mouseup', onMouseUp);
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

<script lang="ts">
	import Main from '../components/Main.svelte';
	import { onMount } from 'svelte';

	onMount(() => {
		if (typeof window !== 'undefined' && window.particlesJS) {
			window.particlesJS.load('particles-js', '/assets/particles.json', () => {
				console.log('Particles loaded');
			});
		}
	});
</script>

<Main />

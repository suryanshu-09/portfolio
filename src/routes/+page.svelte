<script lang="ts">
	import Hero from '../components/Hero.svelte';
	import Stack from '../components/Stack.svelte';
	import Projects from '../components/Projects.svelte';
	import About from '../components/About.svelte';
	import Footer from '../components/Footer.svelte';
</script>

<div class="flex justify-center">
	<div class="max-w-[1400px]">
		<Hero />
		<Stack />
		<!-- <Projects /> -->
		<!-- <About /> -->
	</div>
</div>
<div class="flex justify-center">
	<div class="max-w-[1400px]">
		<Projects />
	</div>
</div>

<div class="flex justify-center">
	<div class="max-w-[1400px]">
		<About />
	</div>
</div>
<Footer />

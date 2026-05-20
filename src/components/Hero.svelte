<script lang="ts">
	import { onMount } from 'svelte';

	let words = ['Fulstack Developer', 'Backend Engineer', 'Android Developer'];
	let currentWord = '';
	let wordIndex = 0;
	let charIndex = 0;
	let isDeleting = false;
	let typingSpeed = 120;
	let delayBetweenWords = 1500;

	function type() {
		let fullWord = words[wordIndex];

		if (isDeleting) {
			currentWord = fullWord.substring(0, charIndex--);
		} else {
			currentWord = fullWord.substring(0, charIndex++);
		}

		if (!isDeleting && charIndex === fullWord.length + 1) {
			setTimeout(() => (isDeleting = true), delayBetweenWords);
		} else if (isDeleting && charIndex < 0) {
			isDeleting = false;
			wordIndex = (wordIndex + 1) % words.length;
			charIndex = 0;
		}

		setTimeout(type, isDeleting ? typingSpeed / 2 : typingSpeed);
	}

	onMount(type);
	$: parts = currentWord.split(/ (.+)/);
</script>

<div class="flex flex-1 flex-col p-4">
	<section id="introPage" class="grid grid-cols-1 gap-10 py-8 sm:py-14 lg:grid-cols-2 lg:gap-4">
		<div class="flex flex-col gap-6 text-center md:gap-8 lg:justify-center lg:gap-10 lg:text-left">
			<h2 class="text-4xl font-semibold sm:text-5xl md:text-6xl">
				Hi! I'm <span class="poppins text-violet-400">Suryanshu,</span>
				<span class="text-3xl underline sm:text-5xl xl:text-6xl xl:no-underline">
					<br />A
					<span class="typewriter">
						<span class="text-violet-400">{parts[0]}</span>
						{#if parts[1]}
							{parts[1]}
						{/if}
					</span>
				</span>
			</h2>

			<p class="text-base sm:text-lg md:text-xl">
				My <b>tech stack</b> includes TypeScript
				<span class="text-violet-400">(NEXT.JS and SvelteKit)</span>, TailwindCSS, Express.js or
				Hono & PostgreSQL and
				<span class="text-violet-400"> Golang</span>.
			</p>

			<a href="#projects">
				<h3 class=" text-xl font-semibold sm:text-2xl md:text-3xl">
					Curious to <span class="poppins text-violet-400">see</span> my work? &DownArrow;
				</h3>
			</a>
		</div>

		<div class="relative grid place-items-center shadow-2xl lg:place-items-end">
			<img src="assets/profilepic.png" alt="Profile Pic" class="z-[2] max-h-[80vh] object-cover" />
		</div>
	</section>
</div>

<style>
	.typewriter {
		font-weight: bold;
		border-right: 2px solid white;
		white-space: nowrap;
		overflow: hidden;
	}
</style>

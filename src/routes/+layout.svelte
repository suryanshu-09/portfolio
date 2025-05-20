<script lang="ts">
	import '../app.css';

	import Footer from '../components/Footer.svelte';
	import Header from '../components/Header.svelte';
	import '../app.css';
	let y = $state(0);

	function goTop() {
		window.scrollTo(0, 0);
	}

	let { children } = $props();
</script>

<div
	class="relative container mx-auto flex min-h-screen w-full max-w-screen flex-col text-sm sm:text-base"
>
	<div
		class={'fixed right-0 bottom-0 z-[10] flex p-10 transition-opacity duration-200 ' +
			(y > 0 ? ' pointer-events-auto opacity-100' : ' pointer-events-none opacity-0')}
	>
		<button
			aria-label="goTop"
			onclick={goTop}
			class="ml-auto grid aspect-square cursor-pointer place-items-center rounded-full bg-slate-900 px-3 text-violet-400 hover:bg-slate-800 sm:px-4"
		>
			<i class="fa-solid fa-arrow-up"></i>
		</button>
	</div>
	<div class="flex justify-center">
		<div class="max-w-[1400px]">
			<Header {y} />
			{@render children()}
		</div>
	</div>
	<Footer />
</div>
<svelte:window bind:scrollY={y} />

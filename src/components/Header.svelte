<script lang="ts">
	let { y } = $props();

	const tabs = [
		{ name: 'Projects ', link: '#projects' },
		{ name: 'About me', link: '#about' }
		// { name: 'Blog', link: 'malema-writes.github.io' }
	];
</script>

<header
	class={'sticky top-0 z-[10] flex items-center justify-between rounded-md border border-solid px-6 duration-200 ' +
		(y > 0 ? ' border-violet-950 bg-slate-950 py-4' : ' border-transparent bg-transparent py-6')}
>
	<div class="poppins text-2xl duration-400 hover:text-violet-400">
		<span class="italic">Suryanshu's</span> <span class="font-extralight">Profile</span>
	</div>
	<div class="hidden items-center gap-4 sm:flex">
		{#each tabs as tab, index (index)}
			<a
				href={tab.link}
				class="duration-200 hover:text-violet-400"
				target={index === 2 ? '_blank' : ''}
			>
				<p>{tab.name}</p>
			</a>
		{/each}
		<a href="https://github.com/suryanshu-09" target="_blank">
			<button
				class="blueShadow group relative overflow-hidden rounded-full bg-white px-5 py-2 text-slate-950"
			>
				<div
					class="absolute top-0 right-full z-0 h-full w-full bg-violet-400 opacity-40 duration-200 group-hover:translate-x-full"
				></div>
				<div class="relative z-9">Get in touch</div>
			</button>
		</a>
	</div>
</header>

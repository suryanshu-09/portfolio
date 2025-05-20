<script lang="ts">
	type ProjectProps = {
		title: string;
		description: string;
		link: string;
		img: string;
		stack?: string[];
	};
	let { title, description, link, img, stack }: ProjectProps = $props();
</script>

<div class="max-w-[90%] rounded-md border border-violet-400 p-4 md:max-w-full">
	<div class="h-[300px] w-full overflow-hidden duration-250 hover:scale-125">
		<img src={img} alt={title} class="h-full w-full rounded-md object-cover" />
	</div>
	<a href={link} target="_blank">
		<h1 class="my-3 text-xl font-medium text-violet-400 duration-200 hover:text-white">
			{title} <i class="fa-solid fa-arrow-up-right-from-square"></i>
		</h1>
	</a>
	<h3 class="text-justify">
		{description}
	</h3>
	{#if stack}
		<div class="scroll-banner mt-3">
			<div class="scroll-banner-inner gap-6">
				{#each [...stack, ...stack] as tech, index (index)}
					<div
						class="rounded-sm border border-violet-400 p-2 font-semibold text-white duration-200 hover:bg-white hover:text-slate-950"
					>
						{tech}
					</div>
				{/each}
			</div>
		</div>
	{/if}
</div>

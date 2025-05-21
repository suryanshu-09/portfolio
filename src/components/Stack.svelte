<script lang="ts">
	import Icon from '@iconify/svelte';
	let technologies = [
		{ title: 'Figma', icon: 'logos:figma', description: 'Design Tool' },
		{ title: 'Next.js', icon: 'logos:nextjs-icon', description: 'FullStack Framework' },
		{ title: 'TypeScript', icon: 'logos:typescript-icon', description: 'JavaScript but better' },
		{ title: 'SvelteKit', icon: 'logos:svelte-icon', description: 'FullStack Framework' },
		{ title: 'Golang', icon: 'logos:gopher', description: "World's simplest language" },
		{ title: 'Docker', icon: 'logos:docker-icon', description: 'Containerisation Tool' },
		{ title: 'Git', icon: 'logos:git-icon', description: 'Version Control System' },
		{ title: 'AWS', icon: 'logos:aws', description: 'Cloud Computing' }
	];
</script>

<div class="flex max-w-[1400px] flex-1 flex-col py-4" id="stack">
	<section class="flex flex-col gap-24 py-20 lg:pt-32 lg:pb-0">
		<div class="flex flex-col gap-2">
			<div class="flex justify-center lg:mr-12 lg:justify-end">
				<div class="text-center lg:text-right">
					<h1 class="my-4 text-3xl font-semibold text-white sm:text-4xl md:text-5xl lg:my-6">
						Current <span class="text-violet-400">technologies</span>
					</h1>
					<p>
						I'm <span class="font-semibold text-violet-400">proficient</span> in a range of modern technologies
						that empower me to build highly functional solutions.
					</p>
					<p>
						These are some of my <span class="font-semibold text-violet-400">main technologies</span
						> stack
					</p>
				</div>
			</div>

			<div class="flex justify-center text-right sm:mx-16 md:mx-10">
				<div
					class="mt-4 grid w-full grid-cols-1 justify-items-center gap-6 sm:grid-cols-2 sm:justify-items-normal md:grid-cols-3 lg:grid-cols-4"
				>
					{#each technologies as { title, icon, description } (title)}
						<div
							class="flex max-w-[90%] min-w-[50vw] justify-between gap-4 rounded-md border border-violet-400 bg-linear-to-r from-slate-800 to-slate-950 p-4 duration-200 hover:scale-110 sm:max-w-full sm:min-w-1"
						>
							<div>
								<Icon {icon} width="56px" height="56px" />
							</div>
							<div>
								<p class="font-bold text-white">{title}</p>
								<p class="text-gray-600">{description}</p>
							</div>
						</div>
					{/each}
				</div>
			</div>
		</div>
	</section>
</div>

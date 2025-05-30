<script lang="ts">
	import CardContent from '$lib/components/ui/card/card-content.svelte';
	import Card from '$lib/components/ui/card/card.svelte';
	import CarouselContent from '$lib/components/ui/carousel/carousel-content.svelte';
	import CarouselItem from '$lib/components/ui/carousel/carousel-item.svelte';
	import CarouselNext from '$lib/components/ui/carousel/carousel-next.svelte';
	import CarouselPrevious from '$lib/components/ui/carousel/carousel-previous.svelte';
	import Carousel from '$lib/components/ui/carousel/carousel.svelte';
	import Icon from '@iconify/svelte';
	let technologies = [
		{ title: 'Golang', icon: 'logos:gopher', description: "World's simplest language" },
		{ title: 'TypeScript', icon: 'logos:typescript-icon', description: 'JavaScript but better' },
		{ title: 'Next.js', icon: 'logos:nextjs-icon', description: 'FullStack Framework' },
		{ title: 'AWS', icon: 'logos:aws', description: 'Cloud Computing' },
		{ title: 'SvelteKit', icon: 'logos:svelte-icon', description: 'FullStack Framework' },
		{ title: 'Docker', icon: 'logos:docker-icon', description: 'Containerisation Tool' },
		{ title: 'Git', icon: 'logos:git-icon', description: 'Version Control System' },
		{ title: 'Figma', icon: 'logos:figma', description: 'Design Tool' }
	];
</script>

<div class="flex max-w-[1400px] flex-1 flex-col sm:py-4" id="stack">
	<section class="flex flex-col sm:gap-24 sm:py-20 lg:pt-32 lg:pb-0">
		<div class="flex flex-col gap-2">
			<div class="mb-3 flex justify-center">
				<div class="text-center">
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

			<div class="hidden justify-center text-right sm:mx-16 sm:flex md:mx-10">
				<div
					class="mt-4 grid w-full grid-cols-1 justify-items-center gap-6 sm:grid-cols-2 sm:justify-items-normal md:grid-cols-3 lg:grid-cols-4"
				>
					{#each technologies as { title, icon, description } (title)}
						<div
							class="flex w-[60vw] justify-between gap-4 overflow-hidden rounded-md border border-violet-400 bg-linear-to-r from-slate-800 to-slate-950 p-4 duration-200 hover:scale-110 sm:max-w-[40vw] md:max-w-[30vw] lg:max-w-[22vw] xl:max-w-[20vw] 2xl:max-w-[16vw]"
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
			<div class="text-right sm:hidden">
				<Carousel class="mt-4 w-[95vw]">
					<CarouselContent class="flex h-[280px] gap-[60px]">
						{#each technologies as { title, icon, description } (title)}
							<CarouselItem class="mx-8 mt-10 basis-2/5">
								<Card
									class="h-[150px] w-[90vw] max-w-[227px] gap-4 overflow-hidden rounded-md border border-violet-400 bg-linear-to-r from-slate-800 to-slate-950 duration-200 hover:scale-110"
								>
									<CardContent class="grid grid-cols-2 gap-2 text-nowrap">
										<Icon {icon} width="48px" height="48px" />
										<p class="text-md self-center font-bold text-white">{title}</p>
										<p class="text-md col-span-2 w-full text-center text-gray-600">
											{description}
										</p>
									</CardContent>
								</Card>
							</CarouselItem>
						{/each}
					</CarouselContent>
					<CarouselPrevious class="top-30 left-2" />
					<CarouselNext class="top-30 right-2" />
				</Carousel>
			</div>
		</div>
	</section>
</div>

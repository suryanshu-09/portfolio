<script lang="ts">
	import * as Card from '$lib/components/ui/card/index.js';
	import CarouselContent from '$lib/components/ui/carousel/carousel-content.svelte';
	import CarouselItem from '$lib/components/ui/carousel/carousel-item.svelte';
	import CarouselNext from '$lib/components/ui/carousel/carousel-next.svelte';
	import CarouselPrevious from '$lib/components/ui/carousel/carousel-previous.svelte';
	import Carousel from '$lib/components/ui/carousel/carousel.svelte';
	type ProjectProps = {
		title: string;
		description: string;
		link: string;
		img: string;
		stack?: string[];
	};

	let ui_ux = [
		{
			title: 'Travelling App',
			img: 'assets/travellingapp.png',
			description: 'Desgined a travelling app from scratch for a design hackathon.',
			link: 'https://www.figma.com/design/RzDbm61DtOjMPO8k3CYygb/Portfolio?node-id=2-1054'
		},
		{
			title: 'Voting App',
			img: 'assets/votingapp.png',
			description:
				'Designed a voting application from scratch (from wireframe to prototyping) as part of my internship.',
			link: 'https://www.figma.com/design/RzDbm61DtOjMPO8k3CYygb/Portfolio?node-id=1-5'
		},
		{
			title: 'Web Pages',
			img: 'assets/webpages.png',
			description:
				'Designed and redesigned web-components and hero sections as part of my internship.',
			link: 'https://www.figma.com/design/RzDbm61DtOjMPO8k3CYygb/Portfolio?node-id=1-3'
		},
		{
			title: 'Prototypes',
			img: 'assets/prototypes.png',
			description: 'Desgined custom prototypes like paralax and animated background.',
			link: 'https://www.figma.com/design/RzDbm61DtOjMPO8k3CYygb/Portfolio?node-id=1-2'
		}
	];
	let dev = [
		{
			title: 'Hulaki',
			img: 'assets/hulaki.gif',
			description:
				'Hulaki brings the power of Postman to your terminal. Crafted with Go, Cobra, and Fang for CLI magic, and powered by Huh and Bubbletea for an elegant TUI experience. Seamlessly test APIs — from HTTP and GraphQL to gRPC — all without leaving your terminal.',
			link: 'https://github.com/suryanshu-09/hulaki',
			stack: ['Go', 'Cobra', 'Bubbletea', 'Postman', 'HTTP', 'GraphQl', 'gRPC']
		},
		{
			title: 'Webmellon',
			img: 'assets/webmellon.jpg',
			description:
				'WebMellon is a full-stack bookmark aggregator that lets users create, manage, and organize catalogues of websites which uses Prometheus for metrics and Grafana for visualisation',
			link: 'https://webmellon.vercel.app/',
			stack: [
				'Next.js',
				'NextAuth',
				'Docker',
				'Shadcn',
				'Postgres',
				'Prisma',
				'Prometheus',
				'Grafana'
			]
		},
		{
			title: 'We Go Wayback',
			img: 'assets/we-go-wayback.gif',
			description:
				"A Golang Implementation of Wayback Machine's wayback_discover_diff. Serves with Go-Chi, Asynq for managing jobs with Redis for backend support and Statsd for metrics.",
			link: 'https://github.com/suryanshu-09/we-go-wayback',
			stack: ['Golang', 'Python', 'Redis', 'Simhash', 'Asynq', 'Go-Chi', 'Http', 'Statsd', 'Docker']
		},
		{
			title: 'RSS Feed',
			img: 'assets/feed.jpg',
			description:
				'Get your favourite feeds, all in one place! From Youtube to WordPress to News, fetch the latest up to date articles and videos using Feed',
			link: 'https://github.com/suryanshu-09/webmellon',
			stack: ['Next.js', 'NextAuth', 'rss-parser', 'Shadcn']
		}
	];
</script>

<main class="flex flex-1 flex-col sm:p-4">
	<section class="flex flex-col gap-24 py-20 lg:py-32" id="projects">
		<div class="flex flex-col gap-2 text-center">
			<h6 class="text-large sm:text-xl md:text-2xl">A few of my creative endeavors.</h6>

			<div>
				<h3 class="my-4 text-3xl font-semibold text-violet-400 sm:text-4xl md:text-5xl lg:my-6">
					Development
				</h3>
				<!-- <div class="grid grid-cols-1 justify-items-center gap-10 md:grid-cols-2 2xl:grid-cols-3"> -->
				<!-- 	{#each dev as { title, img, description, link, stack }, index (index)} -->
				<!-- 		{@render project({ title, img, description, link, stack })} -->
				<!-- 	{/each} -->
				<!-- </div> -->
				<div class="mx-auto w-full">
					<Carousel class="sm:p-2">
						<CarouselContent class="mx-auto -ml-4 max-w-[90vw] sm:gap-4">
							{#each dev as { title, img, description, link, stack }, index (index)}
								{@render projectCarousel({ title, img, description, link, stack })}
							{/each}
						</CarouselContent>
						<CarouselPrevious class="-left-6 md:-left-10 2xl:-left-15" />
						<CarouselNext class="-right-6 md:-right-10 2xl:-right-15" />
					</Carousel>
				</div>
			</div>

			<div>
				<h3 class="my-4 text-3xl font-semibold text-violet-400 sm:text-4xl md:text-5xl lg:my-6">
					UI/UX
				</h3>
				<!-- <div class="grid grid-cols-1 justify-items-center gap-10 md:grid-cols-2 2xl:grid-cols-3"> -->
				<!-- 	{#each ui_ux as { title, img, description, link }, index (index)} -->
				<!-- 		{@render project({ title, img, description, link })} -->
				<!-- 	{/each} -->
				<!-- </div> -->
				<div class="mx-auto w-full">
					<Carousel class="sm:p-2">
						<CarouselContent class="mx-auto -ml-4 max-w-[90vw] sm:gap-4">
							{#each ui_ux as { title, img, description, link }, index (index)}
								{@render projectCarousel({ title, img, description, link })}
							{/each}
						</CarouselContent>
						<CarouselPrevious class="-left-6 md:-left-10 2xl:-left-15" />
						<CarouselNext class="-right-6 md:-right-10 2xl:-right-15" />
					</Carousel>
				</div>
			</div>
		</div>
	</section>
</main>

<!-- {#snippet project({ title, img, description, link, stack }: ProjectProps)} -->
<!-- 	<div class="max-w-full rounded-md border border-violet-400 p-4"> -->
<!-- 		<div class="h-[300px] w-full overflow-hidden duration-250 hover:scale-110"> -->
<!-- 			<img src={img} alt={title} class="h-full w-full rounded-md object-cover" /> -->
<!-- 		</div> -->
<!-- 		<a href={link} target="_blank"> -->
<!-- 			<h1 class="my-3 text-xl font-medium text-violet-400 duration-200 hover:text-white"> -->
<!-- 				{title} <i class="fa-solid fa-arrow-up-right-from-square"></i> -->
<!-- 			</h1> -->
<!-- 		</a> -->
<!-- 		<h3 class="text-justify"> -->
<!-- 			{description} -->
<!-- 		</h3> -->
<!-- 		{#if stack} -->
<!-- 			<div class="scroll-banner mt-4"> -->
<!-- 				<div class="scroll-banner-inner gap-6"> -->
<!-- 					{#each [...stack, ...stack, ...stack] as tech, index (index)} -->
<!-- 						<div -->
<!-- 							class="rounded-sm border border-violet-400 p-2 font-semibold text-white duration-200 hover:bg-white hover:text-slate-950" -->
<!-- 						> -->
<!-- 							{tech} -->
<!-- 						</div> -->
<!-- 					{/each} -->
<!-- 				</div> -->
<!-- 			</div> -->
<!-- 		{/if} -->
<!-- 	</div> -->
<!-- {/snippet} -->

{#snippet projectCarousel({ title, img, description, link, stack }: ProjectProps)}
	<CarouselItem class="ml-4 pl-1 md:basis-3/5 lg:basis-1/2 xl:basis-2/5 2xl:basis-48/100">
		<div class="p-1">
			<Card.Root class="overflow-hidden rounded-md border border-violet-400 md:max-w-[55vw]">
				<Card.Content class="flex-col items-center justify-center p-6">
					<div class="h-[300px] w-full overflow-hidden duration-250 hover:scale-110">
						<img src={img} alt={title} class="h-full w-full rounded-md object-cover" />
					</div>
					<a href={link} target="_blank">
						<h1 class="mt-4 text-xl font-medium text-violet-400 duration-200 hover:text-white">
							{title} <i class="fa-solid fa-arrow-up-right-from-square"></i>
						</h1>
					</a>
					<h3 class="mb-3 text-justify">
						{description}
					</h3>
					{#if stack}
						<div class="scroll-banner mt-4">
							<div class="scroll-banner-inner gap-6">
								{#each [...stack, ...stack, ...stack] as tech, index (index)}
									<div
										class="rounded-sm border border-violet-400 p-2 font-semibold text-white duration-200 hover:bg-white hover:text-slate-950"
									>
										{tech}
									</div>
								{/each}
							</div>
						</div>
					{/if}
				</Card.Content>
			</Card.Root>
		</div>
	</CarouselItem>
{/snippet}

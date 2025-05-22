<script lang="ts">
	type ProjectProps = {
		title: string;
		description: string;
		link: string;
		img: string;
		stack?: string[];
	};

	let ui_ux = [
		{
			title: 'Voting App',
			img: 'assets/votingapp.png',
			description:
				'Designed a voting application from scratch (from wireframe to prototyping) in figma as part of my internship.',
			link: 'https://www.figma.com/design/RzDbm61DtOjMPO8k3CYygb/Portfolio?node-id=1-5'
		},
		{
			title: 'Travelling App',
			img: 'assets/travellingapp.png',
			description: 'Desgined a travelling app from scratch for a design hackathon in figma.',
			link: 'https://www.figma.com/design/RzDbm61DtOjMPO8k3CYygb/Portfolio?node-id=2-1054'
		},
		{
			title: 'Web Pages',
			img: 'assets/webpages.png',
			description: 'Designed websites as part of my internship in figma.',
			link: 'https://www.figma.com/design/RzDbm61DtOjMPO8k3CYygb/Portfolio?node-id=1-3'
		}
	];
	let dev = [
		{
			title: 'Webmellon',
			img: 'assets/webmellon.jpg',
			description:
				'WebMellon is a full-stack bookmark aggregator that lets users create, manage, and organize catalogues of websites.',
			link: 'https://webmellon.vercel.app/',
			stack: ['Next.js', 'NextAuth', 'Docker', 'ShadCN']
		},
		{
			title: 'Business Cards',
			img: 'assets/businessCards.png',
			description:
				'Create, read, update and delete your business cards with this application. Authentication with JWT.',
			link: 'https://github.com/suryanshu-09/Business-Cards',
			stack: ['Mongo', 'Express', 'React', 'Node.js']
		},
		{
			title: 'Portfolio',
			img: 'assets/preview.png',
			description:
				'This very website was built with SvelteKit. I created it as a project to explore the hype around Svelte and learn along the way.',
			link: 'https://suryanshu-profile.vercel.app',
			stack: ['SvelteKit', 'Vercel', 'Svelte5', 'TypeScript']
		}
	];
</script>

<main class="flex flex-1 flex-col p-4">
	<section class="flex flex-col gap-24 py-20 lg:py-32" id="projects">
		<div class="flex flex-col gap-2 text-center">
			<h6 class="text-large sm:text-xl md:text-2xl">A few of my creative endeavors.</h6>

			<div>
				<h3 class="my-4 text-3xl font-semibold text-violet-400 sm:text-4xl md:text-5xl lg:my-6">
					Development
				</h3>
				<div class="grid grid-cols-1 justify-items-center gap-10 md:grid-cols-2 2xl:grid-cols-3">
					{#each dev as { title, img, description, link, stack }, index (index)}
						{@render project({ title, img, description, link, stack })}
					{/each}
				</div>
			</div>

			<div>
				<h3 class="my-4 text-3xl font-semibold text-violet-400 sm:text-4xl md:text-5xl lg:my-6">
					UI/UX
				</h3>
				<div class="grid grid-cols-1 justify-items-center gap-10 md:grid-cols-2 2xl:grid-cols-3">
					{#each ui_ux as { title, img, description, link }, index (index)}
						{@render project({ title, img, description, link })}
					{/each}
				</div>
			</div>
		</div>
	</section>
</main>

{#snippet project({ title, img, description, link, stack }: ProjectProps)}
	<div class="max-w-full rounded-md border border-violet-400 p-4">
		<div class="h-[300px] w-full overflow-hidden duration-250 hover:scale-110">
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
	</div>
{/snippet}

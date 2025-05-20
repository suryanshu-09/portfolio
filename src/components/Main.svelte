<script lang="ts">
	import Project from './Project.svelte';

	let about = [
		{
			name: 'a passionate developer',
			description:
				"My love for computers began when I got my first personal computer in 9th grade. Ever since, I've been breaking my Arch setup and fixing it. This passion for figuring things out has led me to write my own scripts and applets*, building software I actually use myself."
		},
		{
			name: 'a product design & UX fanatic',
			description:
				'Carefully crafting and designing meaningful user experiences allows me to express and experiment with every morsel of creativity I have. I enjoy the challenge of learning new design concepts and enabling users with delightful online experiences.'
		},
		{
			name: 'an avid follower of the RTFM cult',
			description:
				"Diving deep into manuals and tinkering with software is how I learn best. It's how I riced my Hyprland setup, and now I'm learning Go by exploring the official docs and building a TUI frontend for WhatsApp."
		}
	];

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
			img: 'assets/preview.jpg',
			description:
				'This very website was built with SvelteKit. I created it as a project to explore the hype around Svelte and learn along the way.',
			link: 'https://suryanshu-profile.vercel.app',
			stack: ['SvelteKit', 'Vercel', 'Svelte5', 'TypeScript']
		}
	];
</script>

<main class="flex flex-1 flex-col p-4">
	<section id="introPage" class="grid grid-cols-1 gap-10 py-8 sm:py-14 lg:grid-cols-2 lg:gap-4">
		<div class="flex flex-col gap-6 text-center md:gap-8 lg:justify-center lg:gap-10 lg:text-left">
			<h2 class="text-4xl font-semibold sm:text-5xl md:text-6xl">
				Hi! I'm <span class="poppins text-violet-400">Suryanshu</span>
				<br />A
				<span class="poppins text-violet-400">Full Stack</span> Developer
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

		<div class="relative grid place-items-center shadow-2xl">
			<img src="assets/profilepic.png" alt="Profile Pic" class="z-[2] max-h-[70vh] object-cover" />
		</div>
	</section>

	<section class="flex flex-col gap-24 py-20 lg:py-32" id="projects">
		<div class="flex flex-col gap-2 text-center">
			<h6 class="text-large sm:text-xl md:text-2xl">A few of my creative endeavors.</h6>

			<div>
				<h3 class="my-4 text-3xl font-semibold text-violet-400 sm:text-4xl md:text-5xl lg:my-6">
					Development
				</h3>
				<div class="grid grid-cols-1 justify-items-center gap-10 md:grid-cols-2 2xl:grid-cols-3">
					{#each dev as { title, img, description, link, stack }, index (index)}
						<Project {title} {img} {description} {link} {stack} />
					{/each}
				</div>
			</div>

			<div>
				<h3 class="my-4 text-3xl font-semibold text-violet-400 sm:text-4xl md:text-5xl lg:my-6">
					UI/UX
				</h3>
				<div class="grid grid-cols-1 justify-items-center gap-10 md:grid-cols-2 2xl:grid-cols-3">
					{#each ui_ux as { title, img, description, link }, index (index)}
						<Project {title} {img} {description} {link} />
					{/each}
				</div>
			</div>
		</div>
	</section>

	<section
		id="about"
		class="relative flex flex-col gap-16 py-20 pt-10 sm:gap-20 md:gap-24 lg:py-32 lg:pt-16"
	>
		<div
			class="relative flex flex-col gap-2 py-4 text-center before:absolute before:top-0 before:left-0 before:h-1.5 before:w-2/3 before:bg-violet-700 after:absolute after:right-0 after:bottom-0 after:h-1.5 after:w-2/3 after:bg-violet-700"
		>
			<h6 class="text-large sm:text-xl md:text-2xl">Want to know more?</h6>
			<h3 class="text-3xl font-semibold sm:text-4xl md:text-5xl">
				A bit <span class="poppins text-violet-400">about</span> me.
			</h3>
		</div>
		<p class="poppins mx-auto text-lg font-semibold sm:text-xl md:text-2xl">I am . . .</p>
		<div class="mx-auto flex w-full max-w-[800px] flex-col gap-20">
			{#each about as me, index (index)}
				<div class="flex gap-6 sm:gap-8">
					<p class="poppins text-4xl font-semibold text-slate-500 sm:text-5xl md:text-6xl">
						0{index + 1}
					</p>
					<div class="flex flex-col gap-6 sm:gap-8">
						<h3 class="text-2xl sm:text-3xl md:text-5xl">
							{me.name}
						</h3>
						<p>{me.description}</p>
					</div>
				</div>
			{/each}
		</div>
	</section>
</main>

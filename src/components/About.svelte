<script lang="ts">
	let about = [
		{
			name: 'a developer in making',
			description:
				"My love for computers began when I got my first personal computer in 9th grade. Ever since, I've been breaking my Arch setup and fixing it. This passion for figuring things out has led me to write my own scripts and applets*, building software I actually use myself."
		},
		{
			name: 'a product design & UX fanatic',
			description:
				'Carefully crafting and designing meaningful user experiences allows me to express and experiment with every morsel of creativity I have. I enjoy the challenge of learning new design concepts and enabling users with delightful online experiences.'
		},
		{
			name: 'an avid follower of the cult of RTFM',
			description:
				"Diving deep into manuals and tinkering with software is how I learn best. It's how I riced my Hyprland setup, and now I'm learning Go by exploring the official docs and building a TUI frontend for WhatsApp."
		}
	];
</script>

<div class="flex flex-1 flex-col p-4">
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
</div>

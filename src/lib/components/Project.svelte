<script>
	export let project;
</script>

<article
	class="relative flex flex-col overflow-hidden rounded bg-slate-800 p-2 md:p-4"
>
	{#if project.image}
		<a
			href={project.repo}
			target="_blank"
			rel="noopener noreferrer"
			class="block relative"
		>
			<img
				class="-m-2 mb-2 aspect-video h-auto w-[calc(theme(spacing.4)+100%)] max-w-[unset] object-cover md:-m-4 md:mb-2 md:w-[calc(theme(spacing.8)+100%)]"
				src={project.image}
				alt=""
			/>
		</a>
	{/if}

	<a
		href={project.repo}
		target="_blank"
		rel="noopener noreferrer"
		class="absolute top-0 left-0 p-2 bg-slate-800 rounded-br shadow-lg"
	>
		<h3 class="text-2xl font-semibold">{project.name}</h3>
	</a>

	<p class="{project.tags ? '' : 'mb-auto'} {project.image ? 'mt-1' : 'mt-10'}">{project.description}</p>

	{#if project.tags}
		<div class="flex flex-wrap mt-0.5 mb-auto">
			{#each project.tags as tag}
				<div
					class="mr-2 mt-1 text-sm bg-slate-900 p-1.5 rounded text-slate-300"
				>
					{tag}
				</div>
			{/each}
		</div>
	{/if}

	<nav class="flex">
		<a href={project.repo} target="_blank" rel="noopener noreferrer"
			><img
				class="size-7 m-1 mt-2 mr-3"
				src="icons/github.svg"
				alt=""
			/></a
		>
		{#if project.site}
			<a href={project.site} target="_blank" rel="noopener noreferrer"
				><img
					class="size-7 m-1 mt-2"
					src="icons/site.svg"
					alt="Site"
				/></a
			>
		{/if}
	</nav>
</article>

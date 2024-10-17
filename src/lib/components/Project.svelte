<script>
  export let project;
</script>

<article
  class="relative flex flex-col overflow-hidden rounded bg-slate-800 p-2 md:p-4"
>
  <h3
    class="text-2xl font-semibold {project.image
      ? 'absolute top-0 left-0 p-2 bg-slate-800 rounded-br shadow-lg'
      : ''}"
  >
    {project.name}
  </h3>
  {#if project.image}
    <img
      class="-m-2 mb-2 aspect-video h-auto w-[calc(theme(spacing.4)+100%)] max-w-[unset] object-cover md:-m-4 md:mb-2 md:w-[calc(theme(spacing.8)+100%)]"
      src={project.image}
      alt=""
    />
  {/if}
  <p class="mb-auto mt-1">{project.description}</p>
  <nav class="flex">
    <a href={project.repo} target="_blank" rel="noopener noreferrer"
      ><img class="size-7 m-1 mt-2 mr-3" src="icons/github.svg" alt="" /></a
    >
    {#if project.site}
      <a href={project.site} target="_blank" rel="noopener noreferrer"
        ><img class="size-7 m-1 mt-2" src="icons/site.svg" alt="Site" /></a
      >
    {/if}
  </nav>
</article>

<script>
    import Project from "$lib/components/Project.svelte";
    import {projects} from "$lib/projects.js";
</script>

<svelte:head>
    <title>Projects | Bernardo Campos</title> 
</svelte:head>

<h2 class="text-4xl max-w-screen-xl m-auto mb-5">Projects</h2>

<div class="max-w-screen-xl mx-auto grid grid-cols-1 gap-4 sm:grid-cols-[repeat(auto-fill,minmax(theme(spacing.64),1fr))]">
    {#each projects as proj}
        <Project project={proj} />
    {/each}
</div>


<div class="bg-slate-800 text-2xl max-w-screen-xl m-auto my-10 rounded hover:bg-slate-700 transition duration-300" >
    <a class="h-full w-full block p-8 flex items-center justify-center" href="https://github.com/6ernardo" target="_blank" rel="noopener noreferrer">
        Checkout my <img class="size-10 m-1.5" src="icons/github.svg" alt=""> for more projects!
    </a>
</div>



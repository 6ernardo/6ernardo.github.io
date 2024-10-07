<script>
    import { contacts } from '$lib/contacts.js';

    let show_message = false;

    function copyToClip(text){
        navigator.clipboard.writeText(text);
        show_message = true;

        setTimeout(() => {
            show_message = false;
        }, 2000);
    }

</script>

<h2 class="text-4xl max-w-screen-xl m-auto mb-5">Contact me</h2>

{#each contacts as cont}
    <div class="bg-slate-800 text-2xl max-w-screen-xl m-auto my-10 rounded hover:bg-slate-700 transition duration-300" >
        {#if cont.link}
            <a class="h-full w-full block p-8 flex items-center justify-center" 
                href={cont.link} target="_blank" rel="noopener noreferrer">
                {@html cont.html}
            </a>
        {:else}
            <p class="h-full w-full block p-11 flex items-center justify-center hover:cursor-pointer" on:click={() => copyToClip(cont.copy)}>
                {@html cont.html}
            </p>
        {/if}
    </div>
{/each}

{#if show_message}
    <div class="fixed bottom-20 left-1/2 transform -translate-x-1/2 bg-slate-700 p-4 rounded shadow-lg">
        <p>Copied to clipboard!</p>
    </div>
{/if}
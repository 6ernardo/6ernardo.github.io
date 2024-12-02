<script>
    import { page } from '$app/stores';

    $: index = $page.url.pathname === '/'  // styling of header will vary depending on where you are on the site

    const tabs = [
        { text: 'projects', link: '/projects' },
        { text: 'cv', link: '/cv' },
        { text: 'contact', link: '/contact' },
    ]
</script>

<header class="{index ? 
                'h-screen w-screen flex justify-center items-center bg-slate-800' 
                : 'sticky top-0 z-50 bg-slate-800 shadow-md p-2 mb-4'}">
     <nav class={index ? 'text-center' : 'flex justify-between items-center'}>
        <a class={index ? 'block mb-4 text-6xl' : 'text-2xl'} 
            href="/"><h1>Bernardo <b class={index ? 'font-bold' : ''}>Campos</b></h1>
        </a>
        <div class={index ? 'space-x-12' : 'flex space-x-6'}>
            {#each tabs as t}
                <a class={index ? 'text-2xl p-2 py-1 hover:bg-slate-600 rounded transition duration-200' 
                        : ($page.url.pathname === t.link) ? 'p-1 bg-slate-600 rounded' : 'p-1'}
                href={t.link} aria-current={$page.url.pathname === t.link}>{t.text}</a>
            {/each}
        </div>
    </nav>
</header>

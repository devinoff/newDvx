<script lang='ts'>
    import PageContainer from '@/components/PageContainer.svelte';

    const links: { id: number, label: string, url: string, image: string }[] = [
        { id: 1, label: 'Steam', url: 'https://steamcommunity.com/id/dvx_lv', image: 'steam' },
        { id: 2, label: 'Spotify', url: 'https://open.spotify.com/user/31zssuy6wcne32r6tqwdwh5k2xtq', image: 'spotify' },
        { id: 3, label: 'last.fm', url: 'https://www.last.fm/user/dvx_lv', image: 'lastfm' }
    ];

    $effect(() => { document.body.style.backgroundColor = getComputedStyle(document.documentElement).getPropertyValue('--green').trim() });
</script>

<title>homepage</title>

<PageContainer newClass='bg-green'>
    <div class='h-full flex flex-col justify-center items-center gap-2 text-center px-4'>
        <img src='drawings/hithisis.png' class='' alt='hi this is my webpage' />
        <img src='drawings/youcansee.png' class='max-h-[48px]' alt="you can see what I'm into here" />
        <div class='flex flex-col mt-8'>
            {#each links as link, i (link.id)}
                <a href={link.url} target='_blank' class={`w-full flex justify-center items-center gap-4 bg-green hover:scale-110 hover:rounded-md transition-[scale,border-radius] duration-200 ease-in-out border-2 -mt-[2px] ${i === 0 ? 'rounded-t-md' : i === links.length - 1 ? 'rounded-b-md' : ''}`}>
                    <img src={`drawings/${link.image}L.png`} class='max-w-[40px]' alt={`${link.label} logo`} />
                    <img src={`drawings/${link.image}T.png`} class='h-[60%]' alt={`${link.label} text`} />
                </a>
            {/each}
        </div>
    </div>
</PageContainer>
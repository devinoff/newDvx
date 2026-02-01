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
    <div class='p-4'>
        <h1>
            this is my homepage. hello.
        </h1>
    </div>
</PageContainer>

<div class='md:absolute top-5 right-10 grid grid-cols-3 text-center md:flex md:flex-col gap-3 bg-orange px-4 py-3 md:py-2 md:border-2 md:border-black rounded-xl md:rounded-md'>
    <img src='drawings/myLinks.png' class='h-6 col-span-3 mx-auto' alt='my social links are below' />
    {#each links as link (link.id)}
        <a href={link.url} target='_blank' class='w-full flex max-md:justify-center items-center gap-2'>
            <img src={`logos/${link.image}.png`} class='max-w-[28px]' alt={`${link.label} logo`} />
            <img src={`drawings/${link.image}Text.png`} class='h-6 max-xs:hidden' alt={`${link.label} text`} />
        </a>
    {/each}
</div>
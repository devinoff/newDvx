<script>
    import PageContainer from '@/components/PageContainer.svelte';
    $effect(() => { document.body.style.backgroundColor = getComputedStyle(document.documentElement).getPropertyValue('--purple').trim() });
</script>

<title>I love metamorphosis so much</title>

<PageContainer newClass='bg-purple'>
    <div class='h-full px-4 py-8 flex flex-col justify-center items-center gap-2 text-center text-gold'>
        <img src='ashnikko-hex-compressed.jpg' alt='ashnikko hex compilation cover' class='w-full max-w-[300px] rounded-xl' />
        <h1 class='text-4xl text-gold font-bold mt-10 -rotate-2 demonRush'>HEX <span class='text-xl'>[Ashnikko]</span></h1>
        <p class='max-w-[400px] -rotate-2'>This is a fan-curated collection of unreleased tracks by Ashnikko</p>
        <p class='mt-10 demonRush text-xl'>Tracklist:</p>
        <div class='text-left max-w-[200px] flex flex-col gap-[4px] text-sm text-balance'>
            <span>1. Build A Babe</span>
            <span>2. 5 Star</span>
            <span>3. Already Over</span>
            <span>4. Bad For You</span>
            <span>5. Bet You Would</span>
            <span>6. Bop It</span>
            <span>7. Creepy</span>
            <span>8. Cyborg</span>
            <span>9. Future Crazy Ex</span>
            <span>10. Girlfriend</span>
            <span>11. Godzilla</span>
            <span>12. Karma</span>
            <span>13. Halloweenie VII: Night of the Banshee</span>
            <span>14. Krokodil</span>
            <span>15. Metamorphosis</span>
            <span>16. Narcissus</span>
            <span>17. Scared of Me</span>
            <span>18. Wild</span>
        </div>
        <p class='text-sm mt-10 text-balance'>If you want this taken down please contact at info@dvx.lv</p>
    </div>
</PageContainer>

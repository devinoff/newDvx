<script lang='ts'>
	import './layout.css';
	import favicon from '$lib/assets/favicon.svg';
    import {resolve} from '$app/paths';

	let { children } = $props();

    const menuItems: { id: number, label: string, drawing: string, url: '/' | '/links' | '/utilo' | '/hex', textClass?: string, svgClass?: string, linkClass?: string }[] = [
        { id: 1, label: 'homepage', drawing: 'home', url: '/', linkClass: 'col-span-2' },
        { id: 3, label: 'utility tools', drawing: 'utilo', url: '/utilo', svgClass: 'text-blue' },
        { id: 4, label: 'fan-made compilation of ashnikko tracks', drawing: 'hex', url: '/hex', svgClass: 'text-purple' }
    ]
</script>

<style>
    @media (hover: hover) and (pointer: fine) {
        .menuLink {
            transition: rotate 0.4s ease-in-out;
        }
        .menuLink:hover {
            rotate: 2deg;
        }
        .menuLink:nth-child(even):hover {
            rotate: -2deg;
        }
        .rect-dash {
            transition: stroke-dasharray 0.4s ease-in-out, stroke-width 0.4s ease-in-out;
        }
        .menuLink:hover .rect-dash {
            stroke-dasharray: 4 2 6 3;
            stroke-width: 8;
        }
    }
</style>

<svelte:head>
    <link rel='icon' href={favicon} />
</svelte:head>

<section class='md:fixed max-md:w-full md:top-[50dvh] md:-translate-y-[50%] md:ml-4 grid grid-cols-1 xxs:grid-cols-2 md:flex md:flex-col gap-3 bg-cream p-2 md:rounded-md hover:opacity-100 transition-opacity duration-[0.4s] md:opacity-60 xl:opacity-100 z-50'>
    {#each menuItems as item (item.id)}
        <a href={resolve(item.url)} class={`menuLink w-full flex justify-center items-center px-4 py-2 relative text-green text-center ${item.linkClass}`} title={`link for ${item.label}`}>
            <svg class={`absolute top-0 left-0 w-full h-full ${item.svgClass}`} width='100%' height='100%'>
                <rect x='0' y='0' width='100%' height='100%' fill='none' stroke='currentColor' stroke-width='8' rx='10' ry='10' stroke-dasharray='2 2 5 5' class='rect-dash' />
            </svg>
            <img src={`drawings/${item.drawing}.png`} class='h-8' alt={`text saying ${item.label}`} />
        </a>
    {/each}
</section>

{@render children()}

<section class='max-md:hidden fixed bottom-0 left-0 w-full bg-green text-black font-bold text-nowrap whitespace-nowrap overflow-hidden'>
    <div class='w-fit px-8 py-1 circleMe'><img src='drawings/surfing.png' alt='welcome to dvx.lv' class='h-8' /></div>
</section>

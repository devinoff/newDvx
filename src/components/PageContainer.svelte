<script lang='ts'>
    let { children, newClass } = $props();
</script>

<main class={`w-full flex-1 flex max-md:mt-[132px] ${newClass}`}>
    <div class='max-w-[800px] flex-1 my-10 md:mt-0 mx-auto'>
        {@render children()}
    </div>
</main>
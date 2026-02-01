<script lang='ts'>
    let { children, newClass } = $props();
</script>

<main class={`w-full flex-1 flex ${newClass}`}>
    <div class='max-w-[800px] flex-1 md:mb-10 mx-auto'>
        {@render children()}
    </div>
</main>
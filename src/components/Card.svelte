<script>
    let { title, link, className, children} = $props();
</script>

<div class="home-card {className}">
    {#if title}
    <div class="card-top">
        <h1>{title}</h1>
        {#if link}
        <img src="/src/lib/assets/external-link.svg"/>
        {/if}
    </div>
    {/if}
    <div class="card-content">
        {#if !children}
        <p>Under construction</p>
        {/if}
        {@render children?.()}
    </div>
</div>
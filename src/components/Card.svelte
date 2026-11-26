<style lang="scss">
     @import '../scss/card.scss';
</style>
<script lang="ts">
    import type { Snippet } from 'svelte';

    type Props = {
        title?: string;
        link?: string;
        className?: string;
        children?: Snippet;
    };

    let { title, link, className = '', children }: Props = $props();
</script>

{#if link}
<div class="home-card {className}">
    <a
        href={link}
        class="card-link"
        aria-label={title ? `Open ${title}` : 'Open card'}
    ></a>
    {#if title}
    <div class="card-top">
        <h1>{title}</h1>
    <svg class="external-link-icon" viewBox="0 0 24 24" fill="none" aria-hidden="true">
        <path
            d="M10 5H8.2C7.08 5 6.52 5 6.09 5.22a2 2 0 0 0-.87.87C5 6.52 5 7.08 5 8.2v7.6c0 1.12 0 1.68.22 2.11a2 2 0 0 0 .87.87c.43.22.99.22 2.11.22h7.6c1.12 0 1.68 0 2.11-.22a2 2 0 0 0 .87-.87c.22-.43.22-.99.22-2.11V14M20 9V4m0 0h-5m5 0-7 7"
            stroke="currentColor"
            stroke-width="2"
            stroke-linecap="round"
            stroke-linejoin="round"
        />
    </svg>
    </div>
    {/if}
    <div class="card-content">
        {#if !children}
        <p>Under construction</p>
        {/if}
        {@render children?.()}
    </div>
</div>
{:else}
<div class="home-card {className}">
    {#if title}
    <div class="card-top">
        <h1>{title}</h1>
    </div>
    {/if}
    <div class="card-content">
        {#if !children}
        <p>Under construction</p>
        {/if}
        {@render children?.()}
    </div>
</div>
{/if}
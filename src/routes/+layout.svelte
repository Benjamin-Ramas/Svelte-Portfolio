<script lang="ts">
    import favicon from '#lib/assets/favicon.svg';
    import type { LayoutProps } from './$types';

    let { children }: LayoutProps = $props();
</script>

<style lang="scss">
    :global(:root) {
        --primary-background: #dedede;
        --secondary-background: #4d3760;
        --highlight-colour: #0099ff;
        color-scheme: light;
    }

    :global(:root[data-theme='midnight']) {
        --primary-background: #17131f;
        --secondary-background: #eee7f5;
        --highlight-colour: #56c8ff;
        color-scheme: dark;
    }

    :global(:root[data-theme='ocean']) {
        --primary-background: #d9f0f3;
        --secondary-background: #12475a;
        --highlight-colour: #007f9e;
        color-scheme: light;
    }

    :global(:root[data-theme='forest']) {
        --primary-background: #e4ecd9;
        --secondary-background: #2d4a3b;
        --highlight-colour: #bd6a3d;
        color-scheme: light;
    }
</style>

<svelte:head>
    <script>
        const savedTheme = localStorage.getItem('portfolio-theme');
        if (['lavender', 'midnight', 'ocean', 'forest'].includes(savedTheme ?? '')) {
            document.documentElement.dataset.theme = savedTheme;
        }
    </script>
    <link rel="icon" href={favicon} />
    <link
        href="https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100..900;1,100..900&display=swap"
        rel="stylesheet"
    />
</svelte:head>

{@render children()}
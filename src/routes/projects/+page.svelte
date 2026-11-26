<style lang="scss">
    @import '../../scss/projects-page.scss';
</style>

<script>
    import Card from '../../components/Card.svelte';
</script>

<svelte:head>
    <title>Projects | Benjamin Ramas</title>
    <meta name="description" content="My education and professional experience." />
</svelte:head>

<main class="projects-page">
    <a class="back" href="./">Back</a>
    <Card title="Projects">
        <a target="_blank" href="https://github.com/Benjamin-Ramas/Svelte-Portfolio">
        <div>
            <h4>Professional Portfolio Website</h4>
            <p>A portfolio website created with Sveltekit and SCSS currently being hosted on Digital Ocean.</p>
        </div>
        </a>
        <a target="_blank" href="https://blankedslate.itch.io/bullet-looper">
        <div>
            <h4>Bullet Looper</h4>
            <p>A game made for the 2025 GMTK game jam I made as an attempt to learn how to make games in Raylib.</p>
        </div>
        </a>
        <a target="_blank" href="https://blankedslate.itch.io/dungeon-flipper">
        <div>
            <h4>Dungeon Flipper</h4>
            <p>A game made in Godot for Mini Jam 176.</p>
        </div>
        </a>
    </Card>
</main>
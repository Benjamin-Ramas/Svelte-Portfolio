<style lang="scss">
    @import '../scss/home-page.scss';
    @import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100..900;1,100..900&display=swap');
    
</style>
<script lang="ts">
    import { onMount } from 'svelte';
    import Card from '../components/Card.svelte';

    const colorSchemes = [
        { id: 'lavender', name: 'Lavender', background: 'rgb(222, 222, 222)', foreground: '#4d3760' },
        { id: 'midnight', name: 'Midnight', background: '#17131f', foreground: '#eee7f5' },
        { id: 'ocean', name: 'Ocean', background: '#d9f0f3', foreground: '#12475a' },
        { id: 'forest', name: 'Forest', background: '#e4ecd9', foreground: '#2d4a3b' }
    ] as const;
    type ColorSchemeId = (typeof colorSchemes)[number]['id'];

    let selectedScheme = $state<ColorSchemeId>('lavender');

    onMount(() => {
        const savedScheme = colorSchemes.find(
            ({ id }) => id === document.documentElement.dataset.theme
        );
        if (savedScheme) selectedScheme = savedScheme.id;
    });

    function selectScheme(id: ColorSchemeId) {
        selectedScheme = id;
        document.documentElement.dataset.theme = id;
        localStorage.setItem('portfolio-theme', id);
    }
</script>

<main class="home-page">
    <Card title="Welcome" className="welcome">
        <p>Hello I am Benjamin I am a computer science student with experience in both game development and data analysis. I started my journey by learning to make games in Unity and learning C# I then moved on to Python and started taking it seriously as a career opportunity by starting the NQ Computing course in West Lothian. Through them I got an internship to work at RoslinCT. Now the latest chapter in my journey is learning in the University of Dundee.</p>
    </Card>
    <Card title="Theme" className="theme">
        <div class="theme-options" role="group" aria-label="Color scheme">
            {#each colorSchemes as scheme (scheme.id)}
                <button
                    type="button"
                    class="theme-option"
                    aria-pressed={selectedScheme === scheme.id}
                    onclick={() => selectScheme(scheme.id)}
                    >{scheme.name}
                </button>
            {/each}
        </div>
    </Card>
    <Card title="Projects" link="./projects" className="projects">
        <h3>Latest Projects</h3>
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
    <Card title="Experience" link="./experience" className="experience">
        <h3>Education</h3>
        <h4>Computer Science at Dundee University</h4>
        <p>August 2025 - Current</p>
        <h3>Work</h3>
        <h4>Data Analyst at RoslinCT</h4>
        <p>February 2024 - February 2025</p>
    </Card>
    <Card title="Blog" className="blog"></Card>
    <Card title="Contact Me" className="contact-me">
        <p>Phone Number: 07591045445</p>
        <p>Email: benramas911@gmail.com</p>
        <a target="_blank" href="https://uk.linkedin.com/in/benjamin-ramas">Linkedin</a>
        <a target="_blank" href="https://github.com/Benjamin-Ramas">Github</a>
        <a target="_blank" href="https://blankedslate.itch.io/">Itch.io</a>
        <a href="/B_CV.pdf">CV</a>
    </Card>
    <Card title="What I Use" className="what-i-use">
        <h3>Programming Languages</h3>
        <div class="subsection">
            <a target="_blank" href="https://www.c-language.org/">C</a>
            <a target="_blank" href="https://isocpp.org/">C++</a>
            <a target="_blank" href="https://docs.microsoft.com/en-us/dotnet/csharp/">C#</a>
            <a target="_blank" href="https://www.java.com/">Java</a>
            <a target="_blank" href="https://developer.mozilla.org/en-US/docs/Web/JavaScript">Javascript</a>
            <a target="_blank" href="https://www.python.org/">Python</a>
        </div>
        <h3>Data Analysis</h3>
        <div class="subsection">
            <a target="_blank" href="https://www.smartsheet.com/">Smartsheets</a>
            <a target="_blank" href="https://www.microsoft.com/en-us/microsoft-365/excel">Excel</a>
            <a target="_blank" href="https://powerbi.microsoft.com/">PowerBI</a>
        </div>
        <h3>Game Development</h3>
        <div class="subsection">
            <a target="_blank" href="https://godotengine.org/">Godot</a>
            <a target="_blank" href="https://www.raylib.com/">Raylib</a>
            <a target="_blank" href="https://unity.com/">Unity</a>
        </div>
        <h3>Web Development</h3>
        <div class="subsection">
            <a target="_blank" href="https://svelte.dev/docs/kit/introduction">SvelteKit</a>
            <a target="_blank" href="https://sass-lang.com/">SCSS</a>
            <a target="_blank" href="https://nodejs.org/">Nodejs</a>
            <a target="_blank" href="https://react.dev/">Reactjs</a>
            <a target="_blank" href="https://nextjs.org/">Nextjs</a>
        </div>
    </Card>
    <Card className="site-info">
        <p>Created using Sveltekit and SCSS</p>
        <p>Hosted on Digital Ocean</p>
    </Card>
</main>
<style>
    @import '../css/main.css';
    @import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100..900;1,100..900&display=swap');
</style>
<script>
    import Card from '../components/Card.svelte';
</script>

<main>
    <Card title="Welcome" className="welcome">
        <p>Hello I am Benjamin I am a computer science student with experience in both game development and data analysis.</p>
    </Card>
    <Card title="Projects" className="projects">
        <h3>Latest Projects</h3>
        <a>Professional Portfolio Website</a>
    </Card>
    <Card title="Experience" className="experience">
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
        <a>Linkedin</a>
        <a>Github</a>
        <a>Itch.io</a>
    </Card>
    <Card title="Theme" className="theme"></Card>
    <Card title="What I Use" className="what-i-use">
        <h3>Data Analysis</h3>
        <div class="subsection">
            <a>Smartsheets</a>
            <a>Excel</a>
        </div>
        <h3>Game Development</h3>
        <div class="subsection">
            <a>Godot</a>
            <a>Raylib</a>
            <a>Unity</a>
        </div>
        <h3>Web Development</h3>
        <div class="subsection">
            <a target="_blank" href="https://svelte.dev/docs/kit/introduction">SvelteKit</a>
            <a>SCSS</a>
        </div>
    </Card>
    <Card className="site-info">
        <p>Created using Sveltekit</p>
    </Card>
</main>
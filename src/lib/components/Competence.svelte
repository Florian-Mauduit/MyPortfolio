<script>
    import Icons from "./icons.svelte";

    const skills = [
        { name: "React", Icons: "react" },
        { name: "Svelte", Icons: "svelte" },
        { name: "JavaScript", Icons: "js" },
        { name: "HTML", Icons: "html" },
        { name: "CSS", Icons: "css" },
        { name: "Figma", Icons: "figma" },
        { name: "wordpress", Icons: "wordpress" },
        { name: "NodeJs", Icons: "nodeJs" },
        { name: "MySQL", Icons: "mysql" },
        { name: "Git", Icons: "git" },
    ];
</script>

<section class="competence">
    <div>
        <h2 class="titleCompetence">Mes Compétences</h2>
    </div>
    <div class="competenceComp">
        <!-- à prévoir / voir si ça peut être utile mettre l'expérience que j'ai sur les différentes techno avec un système de popup  -->
        <div class="skills-grid">
            {#each skills as skill}
                <div class="skill-card">
                    <Icons name={skill.Icons} />
                    <p>{skill.name}</p>
                </div>
            {/each}
        </div>
    </div>
</section>

<style>
    .competenceComp {
        display: flex;
    }
    .competence {
        display: flex;
        flex-wrap: wrap;
        flex-direction: column;
        justify-content: center;
        flex-basis: auto;
        padding: 6rem 6rem;
        background-color: #283618;
    }

    .competenceList {
        padding: 6rem 6rem;
        color: #fff;
    }

    .skills-section {
        background: #111827;
        color: #0ff;
        padding: 6rem 2rem;
        text-align: center;
    }
    .skills-grid {
        display: flex;
        flex-wrap: wrap;
        flex-basis: 600px;
        justify-content: center;
        justify-content: space-between;
        margin: 0 auto;
        /* width: 600px; */
    }
    .skill-card {
        background: #3a5a40;
        border: 1px solid #a3b18a;
        border-radius: 10px;
        padding: 1rem;
        height: 120px;
        width: 70px;
        margin-right: 10px;
        margin-top: 10px;
        transition:
            transform 0.3s,
            box-shadow 0.3s;
    }
    .skill-card:hover {
        transform: scale(1.05);
        box-shadow:
            0 0 15px #dad7cd,
            0 0 px #dad7cd;
    }
    .skill-card img {
        width: 50px;
        height: 50px;
        object-fit: contain;
        color: #dad7cd;
        /* filter: drop-shadow(0 0 6px #0ff); */
    }
    .skill-card p {
        margin-top: 0.5rem;
        font-size: 1rem;
        color: #dad7cd;
        /* text-shadow: 0 0 4px #0ff; */
    }
</style>

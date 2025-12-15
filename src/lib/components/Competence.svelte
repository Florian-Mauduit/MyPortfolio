<script>
    import Icons from "./icons.svelte";

    const skills = [
        { name: "React", Icons: "react", level: "Avancé" },
        { name: "Svelte", Icons: "svelte", level: "Avancé" },
        { name: "JavaScript", Icons: "js", level: "Avancé" },
        { name: "HTML", Icons: "html", level: "Avancé" },
        { name: "CSS", Icons: "css", level: "Avancé" },
        { name: "Figma", Icons: "figma", level: "Avancé" },
        { name: "wordpress", Icons: "wordpress", level: "Avancé" },
        { name: "NodeJs", Icons: "nodeJs", level: "Avancé" },
        { name: "MySQL", Icons: "mysql", level: "Avancé" },
        { name: "Git", Icons: "git", level: "Avancé" },
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
                    <span class="skill-level">{skill.level}</span>
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
        padding: 6rem 6rem;
        background-color: #283618;
        color: #fefae0;
        text-align: center;
    }

    .titleCompetence {
        font-size: 2rem;
        letter-spacing: 0.08em;
        text-transform: uppercase;
        margin-bottom: 2rem;
    }

    .competenceComp {
        display: flex;
        justify-content: center;
    }

    .skills-grid {
        display: flex;
        flex-wrap: wrap;
        gap: 1.5rem;
        max-width: 700px;
        justify-content: center;
    }

    .skill-card {
        background: #3a5a40;
        border: 1px solid #a3b18a;
        border-radius: 12px;
        padding: 1rem 0.75rem;
        width: 110px;
        height: 130px;

        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;

        transition:
            transform 0.2s ease,
            box-shadow 0.2s ease,
            border-color 0.2s ease;
    }
    .skill-card:hover {
        transform: translateY(-4px);
        box-shadow: 0 10px 20px rgba(0, 0, 0, 0.25);
        border-width: 2px;
        border-color: 5px #fefae0;
    }

    .skill-level {
        margin-top: 0.25rem;
        font-size: 0.75rem;
        color: #fefae0;
        text-transform: uppercase;
        letter-spacing: 0.06em;
    }

    .skill-card img {
        color: #dad7cd;
    }

    .skill-card p {
        margin-top: 0.5rem;
        font-size: 0.9rem;
        font-weight: 600;
        font-size: 1rem;
        color: #fefae0;
    }
</style>

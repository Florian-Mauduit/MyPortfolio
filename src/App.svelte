<script>
  import { fly, fade } from "svelte/transition";
  import Header from "./lib/components/Header.svelte";
  import ProjectCard from "./lib/components/ProjectCard.svelte";
  import Competence from "./lib/components/Competence.svelte";
  import Apropos from "./lib/components/Apropos.svelte";
  import Icons from "./lib/components/icons.svelte";
  import imgPortfolio from "./assets/IMG-portfolio.png";
  import imgForcastFire from "./assets/IMG-forcastFire.png";
  import imgCocktail from "./assets/IMG-cocktail.png";

  let projects = [
    {
      title: "Portfolio",
      description:
        "Projet personnel visant à concevoir un portfolio moderne et performant avec Svelte, reflétant mon profil de développeur web.",
      descriptionModal:
        "Projet personnel visant à concevoir un portfolio moderne et performant pour présenter mes réalisations.",
      technologies: "Technologies : Svelte et TypeScript",
      link: "#",
      image: imgPortfolio,
    },
    {
      title: "Application web – Projet client",
      description:
        "Projet de fin de formation réalisé en équipe pour un client réel, à partir de besoins fonctionnels précis. Ce projet a servi de livrable final dans le cadre de la validation du diplôme.",
      descriptionModal:
        "Projet de fin de formation réalisé en équipe pour un client réel, répondant à des besoins fonctionnels précis et servant à la validation du diplôme.",
      technologies: "Technologies : React, NodeJs, SQL et utilisation d'API",
      link: "https://www.forecast-fire.fr/",
      image: imgForcastFire,
    },
    {
      title: "Application web – Données via API",
      description:
        "Projet en équipe axé sur l’intégration complète d’une API au sein d’une application web.",
      descriptionModal:
        "Projet réalisé en équipe dans le cadre de la formation, permettant de maîtriser l’utilisation d’une API de bout en bout.",
      technologies: "Technologies : React et utilisation d'API",
      link: "https://oeilden8.github.io/UndefinedCocktails/",
      image: imgCocktail,
    },
  ];

  let showCopied = false;
  const email = "florian.mauduit@ikmail.com";

  function copyEmail() {
    try {
      navigator.clipboard.writeText(email).then(() => {
        showCopied = true;
        setTimeout(() => (showCopied = false), 2000);
      });
    } catch (err) {
      console.error("Impossible de copier : ", err);
    }
  }
</script>

<Header />

<main
  style="margin-top: 80px; font-family: 'Arial', sans-serif; line-height: 1.6;"
>
  <section id="home" class="home">
    <h2>Développeur front-end</h2>
    <div class="icon-reseaux">
      <a href="https://github.com/Florian-Mauduit" target="_blank"
        ><Icons name="gitHub" className="gitHub" /></a
      >
      <a href="https://www.linkedin.com/in/florian-mauduit/" target="_blank"
        ><Icons name="linkedin" className="linkedin" /></a
      >
      <a
        href="/cv-florian-mauduit-frontend-2025.pdf"
        target="_blank"
        rel="noopener noreferrer"><Icons name="cv" className="cv" /></a
      >
    </div>
  </section>
  <Apropos />
  <Competence />
  <!-- Projets -->
  <section id="projects" class="containerProjet">
    <h2>Mes projets récents</h2>
    <div class="containerCard">
      {#each projects as project}
        <ProjectCard {...project} />
      {/each}
    </div>
  </section>

  <section class="monCV">
    <h3 class="titleCV">En savoir plus sur mon parcours</h3>
    <p class="pCV">Mon CV est accessibles au téléchargement.</p>
    <a
      class="btnCv"
      href="/cv-florian-mauduit-frontend-2025.pdf"
      target="_blank">Télécharger mon CV</a
    >
  </section>

  <section id="contact" class="containerContact">
    <h2 class="titleContact">Envie d’échanger ?</h2>

    <div class="contact">
      <p>
        Je suis disponible pour discuter d’opportunités ou répondre à vos
        questions.
      </p>
      <div class="email-wrapper">
        <button class="email-btn" on:click={copyEmail}>
          {email}
        </button>

        {#if showCopied}
          <span class="copied-notif"> ✅ Copié ! </span>
        {/if}
      </div>
      <a
        class="btnLinkedin"
        href="https://www.linkedin.com/in/florian-mauduit/"
        target="_blank"
        rel="noopener noreferrer"
        >LinkedIn
      </a>
    </div>
  </section>
</main>

<footer>&copy; 2025 Florian. Tous droits réservés.</footer>

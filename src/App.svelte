<script>
  import Header from "./lib/components/Header.svelte";
  import ProjectCard from "./lib/components/ProjectCard.svelte";
  import Competence from "./lib/components/Competence.svelte";
  import Apropos from "./lib/components/Apropos.svelte";
  import Icons from "./lib/components/icons.svelte";

  let projects = [
    {
      title: "Portfolio",
      description: "Mon portfolio réalisé en Svelte.",
      link: "#",
    },
    { title: "Blog", description: "Blog personnel avec SvelteKit.", link: "#" },
    {
      title: "E-commerce",
      description: "Site e-commerce fictif pour démonstration.",
      link: "#",
    },
  ];
</script>

<Header />

<main
  style="margin-top: 80px; font-family: 'Arial', sans-serif; line-height: 1.6;"
>
  <!-- Accueil -->
  <section
    id="home"
    style="padding: 21rem 2rem; background: #606c38; color: white; text-align: center;"
  >
    <h2 style="font-size: 5.5rem; margin-bottom: 1rem;">
      Développeur front-end
    </h2>
    <!-- <p style="font-size: 1.2rem; max-width: 600px; margin: 0 auto;">
      Développeur web et web designe.
    </p> -->
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
  <section
    id="projects"
    style="padding: 6rem 2rem; background: #f9fafb; text-align: center;"
  >
    <h2 style="font-size: 2rem; margin-bottom: 2rem;">Mes projets</h2>
    <div
      style="display: grid; grid-template-columns: repeat(auto-fit,minmax(280px,1fr)); gap: 2rem; max-width: 1000px; margin: 0 auto;"
    >
      {#each projects as project}
        <ProjectCard {...project} />
      {/each}
    </div>
  </section>

  <section class="monCV">
    <h3>Téléchager mon cv</h3>
    <!-- Crée un bouton pour afficher mon cv en version pdf et un bouton pour le télécharger directement -->
    <!-- Point de vue de la mise en forme les mettre les en column -->
  </section>

  <!-- Contact -->
  <section
    id="contact"
    style="padding: 6rem 2rem; background: #fff; color: white; text-align: center;"
  >
    <!-- Améliorer cet partie pour faire un système de formulaire ou une autre manière de me contact -->
    <h2 style="font-size: 2rem; margin-bottom: 1rem; color: black">Contact</h2>
    <p style="margin-bottom: 1rem; color: black">
      Tu peux me contacter par email à :
    </p>
    <a
      href="mailto:florian.mauduit@ikmail.com"
      style="color: black; font-weight:500;">florian.mauduit@ikmail.com</a
    >
  </section>
</main>

<footer
  style="padding: 2rem; text-align: center; background: #111827; color: #9ca3af;"
>
  &copy; 2025 Florian. Tous droits réservés.
</footer>

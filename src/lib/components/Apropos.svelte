<section class="aPropos">
    <div class="aPropos-container">
        <div class="titre">
            <h2>A propos de moi</h2>
        </div>
        <div class="p-aPropos">
            <p>
                Développeur front-end confirmé avec 3 ans d’expérience en
                start-up sur une plateforme SaaS, je conçois et développe des
                interfaces web performantes et centrées sur l’utilisateur,
                principalement avec React et Svelte. Habitué aux environnements
                agiles, je travaille en étroite collaboration avec les équipes
                produit et design pour transformer des maquettes Figma en
                expériences fluides, accessibles et maintenables.
            </p>
            <p>
                Au quotidien, j’accorde une attention particulière à
                l’optimisation des parcours utilisateurs, à la qualité du code
                et à la performance des applications, qu’il s’agisse de projets
                modernes ou de sites WordPress à maintenir et faire évoluer.
                Autonome, persévérant et doté d’un bon relationnel.
            </p>
            <p class="pDisponible">
                Disponible — télétravail / hybride (Chartres, Orléans, Le Mans,
                Paris) <a
                    class="lienCV"
                    href="/cv-florian-mauduit-frontend-2025.pdf"
                    target="_blank"
                    rel="noopener noreferrer">Télécharger mon CV</a
                >
            </p>
        </div>
    </div>
</section>

<style>
    .aPropos {
        display: flex;
        padding: 8rem 1.5rem;
        min-height: 40vh;
        background: #fefae0; /* exemple fond foncé */
        color: #283618;
    }

    .aPropos-container {
        max-width: 1000px;
        margin: 0 auto;
        display: flex;
        gap: 2.5rem;
        align-items: center;
    }

    .titre {
        flex: 0 0 30%;
        display: flex;
        align-items: center;
        justify-content: center;
        text-align: center;
        border-left: 4px solid currentColor;
        padding-left: 1rem;
    }

    .titre h2 {
        font-size: 2rem;
        letter-spacing: 0.05em;
        text-transform: uppercase;
    }

    .p-aPropos {
        flex: 1;
        max-width: 700px;
        line-height: 1.6;
        font-size: 1rem;
    }

    .pDisponible {
        font-weight: 600;
        font-size: 14px;
    }

    .lienCV {
        text-decoration: underline;
        color: #283618;
        font-size: 16px;
        font-weight: 800;
    }
    .lienCV:hover {
        background-color: #283618;
        color: #fefae0;
        text-decoration: none;
        padding: 3px;
        border-radius: 15px;
    }

    @media (max-width: 768px) {
        .aPropos-container {
            flex-direction: column;
            align-items: stretch;
        }

        .titre {
            justify-content: flex-start;
            text-align: left;
            margin-bottom: 1rem;
        }
    }
</style>

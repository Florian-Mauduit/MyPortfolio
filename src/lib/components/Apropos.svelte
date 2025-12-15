<section class="aPropos">
    <div class="aPropos-container">
        <div class="titre">
            <h2>A propos de moi</h2>
        </div>
        <div class="p-aPropos">
            <p>
                Développeur front-end confirmé, avec 3 ans d’expérience en
                start-up sur une plateforme SaaS, je conçois et développe des
                interfaces React et Svelte centrées sur l’utilisateur. Habitué à
                travailler en méthode agile, j’aime transformer des maquettes
                Figma en expériences fluides, optimiser les parcours
                utilisateurs et maintenir des sites WordPress performants.
                Autonome, persévérant et avec un bon relationnel, je recherche
                de nouvelles opportunités en télétravail ou hybride autour de
                Chartres, Orléans, Le Mans et Paris.
            </p>
        </div>
    </div>
</section>

<style>
    .aPropos {
        display: flex;
        padding: 4rem 1.5rem;
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
        align-items: center; /* centre le h2 verticalement */
        justify-content: center; /* centre horizontalement */
        text-align: center;
        border-left: 4px solid currentColor; /* accent visuel */
        padding-left: 1rem;
    }

    .titre h2 {
        font-size: 2rem;
        letter-spacing: 0.05em;
        text-transform: uppercase;
    }

    .p-aPropos {
        flex: 1;
        max-width: 650px;
        line-height: 1.6;
        font-size: 1rem;
    }

    /* version mobile */
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

<script>
    import { onMount } from "svelte";

    let isAtTop = true;
    let isMenuOpen = false;

    onMount(() => {
        const handleScroll = () => {
            isAtTop = window.scrollY < 10;
        };
        window.addEventListener("scroll", handleScroll);
        return () => window.removeEventListener("scroll", handleScroll);
    });

    let menu = [
        { name: "Projets", id: "projects" },
        { name: "Contact", id: "contact" },
    ];

    const toggleMenu = () => {
        isMenuOpen = !isMenuOpen;
    };

    const closeMenu = () => {
        isMenuOpen = false;
    };
</script>

<header class:is-top={isAtTop}>
    <div class="sectionName">
        <h1 class="title">
            <a href="#" on:click={closeMenu}>Florian Mauduit</a>
        </h1>
    </div>

    <!-- Bouton burger visible en mobile -->
    <button
        class="burger"
        on:click={toggleMenu}
        aria-label="Menu"
        aria-expanded={isMenuOpen}
    >
        <span class:open={isMenuOpen}></span>
        <span class:open={isMenuOpen}></span>
        <span class:open={isMenuOpen}></span>
    </button>

    <nav class="nav-desktop">
        {#each menu as item}
            <a href={"#" + item.id} class="menu-link">{item.name}</a>
        {/each}
    </nav>
    <nav class="nav-mobile {isMenuOpen ? 'open' : ''}">
        {#each menu as item}
            <a href={"#" + item.id} class="menu-link" on:click={closeMenu}>
                {item.name}
            </a>
        {/each}
    </nav>
</header>

<style>
    header {
        position: fixed;
        top: 0;
        width: 100%;
        display: flex;
        justify-content: space-around;
        align-items: center;
        padding: 1rem;
        background: transparent;
        backdrop-filter: blur(4px);
        color: #fefae0;
        transition: all 0.1s ease-in-out;
        z-index: 1000;
    }

    header.is-top {
        background: #283618;
        color: #fefae0;
        backdrop-filter: none;
    }
    header.is-top .menu-link,
    header.is-top .title {
        color: #dad7cd;
    }

    header:hover {
        background-color: #283618;
    }
    header:hover .menu-link,
    header:hover .title {
        color: #dad7cd;
    }

    .sectionName {
        display: flex;
    }

    .menu-link {
        margin-left: 1.5rem;
        font-size: 20px;
        font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
            "Lucida Sans", Arial, sans-serif;
        color: #283618;
        text-decoration: none;
        transition: all 0.3s ease-in-out;
    }
    .menu-link:hover {
        color: #283618;
        text-decoration: underline;
    }

    .title {
        font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
            "Lucida Sans", Arial, sans-serif;
        color: #283618;
    }

    .title a {
        text-decoration: none;
        color: currentColor;
    }

    .title:hover {
        text-decoration: underline;
        cursor: pointer;
    }

    /* NAV desktop = ton nav d'origine */
    .nav-desktop {
        display: flex;
        align-items: center;
    }

    /* Bouton burger (mobile seulement) */
    .burger {
        display: none;
        flex-direction: column;
        justify-content: space-between;
        width: 28px;
        height: 20px;
        background: none;
        border: none;
        padding: 0;
        cursor: pointer;
    }

    .burger span {
        display: block;
        height: 3px;
        width: 100%;
        background: #283618;
        border-radius: 10px;
        transition:
            transform 0.3s ease,
            opacity 0.3s ease,
            background 0.3s ease;
    }

    header.is-top .burger span,
    header:hover .burger span {
        background: #dad7cd;
    }

    /* Animation burger -> X */
    .burger span.open:nth-child(1) {
        transform: translateY(8.5px) rotate(45deg);
    }
    .burger span.open:nth-child(2) {
        opacity: 0;
    }
    .burger span.open:nth-child(3) {
        transform: translateY(-8.5px) rotate(-45deg);
    }

    /* NAV mobile */
    .nav-mobile {
        position: fixed;
        top: 70px; /* hauteur du header */
        left: 0;
        right: 0; /* prend toute la largeur possible */
        width: 100vw; /* GARANTIT largeur totale écran */
        background: #283618;
        display: none;
        flex-direction: column;
        padding: 1rem 1rem 1.5rem; /* padding plus serré */
        gap: 0.75rem;
        max-height: calc(100vh - 64px); /* contraint à la taille de l'écran */
        overflow-y: auto;
        margin: 0; /* supprime marges */
        box-sizing: border-box; /* padding inclus dans largeur */
    }

    .nav-mobile.open {
        display: flex;
    }

    .mobile-link {
        margin-left: 0;
        color: #dad7cd;
    }

    @media (max-width: 600px) {
        .nav-desktop {
            display: none;
        }

        .burger {
            display: flex;
        }

        header {
            justify-content: space-between; /* logo gauche, burger droite */
            padding: 1rem 1rem; /* padding symétrique, pas trop large */
            width: 100vw; /* largeur totale viewport */
            box-sizing: border-box; /* padding inclus dans largeur */
        }

        .sectionName {
            margin: 0; /* supprime marges inutiles */
        }
    }
</style>

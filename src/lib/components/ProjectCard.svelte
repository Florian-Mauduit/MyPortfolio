<script>
    export let title;
    export let description;
    export let descriptionModal;
    export let technologies;
    export let link;
    export let image;

    let showModal = false;

    function openModal() {
        showModal = true;
    }

    function closeModal() {
        showModal = false;
    }
</script>

<div class="card">
    <h3>{title}</h3>
    <div class="card-image">
        <img src={image} alt={title} />
    </div>
    <p>{description}</p>

    {#if link}
        <button class="btnCardOpen" on:click={openModal}>
            Voir le projet
        </button>
    {/if}
</div>

{#if showModal}
    <div class="modal-backdrop" on:click={closeModal}>
        <div class="modal" on:click|stopPropagation>
            <img src={image} alt={title} />

            <div class="modal-actions">
                <div>
                    <p class="descriptionProjet">{descriptionModal}</p>
                    <p class="techno">{technologies}</p>
                </div>
                <div class="btnContainer">
                    <a
                        class="btnModalLink"
                        href={link}
                        target="_blank"
                        rel="noreferrer"
                    >
                        Aller sur le projet
                    </a>
                    <button class="btnModalClose" on:click={closeModal}
                        >Fermer</button
                    >
                </div>
            </div>
        </div>
    </div>
{/if}

<style>
    .btnCardOpen,
    .btnModalClose,
    .btnModalLink {
        margin: 4px;
        padding: 15px;
        border: 2px;
        background: #a3b18a;
        border-radius: 30px;
        color: #fff;
        font-weight: 600;
        font-size: 14px;
        cursor: pointer;
        text-decoration: none;
    }

    .btnContainer {
        display: flex;
        flex-direction: column;
    }

    .btnCardOpen:hover,
    .btnModalClose:hover,
    .btnModalLink:hover {
        background: #3a5a40;
        text-decoration: none;
    }

    .card {
        border: 1px solid #ddd;
        padding: 1rem;
        border-radius: 8px;
    }

    .card-image {
        width: 100%;
        height: 200px;
        overflow: hidden;
        border-radius: 15px;
    }

    .card-image img {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

    .descriptionProjet,
    .techno {
        font-weight: 600;
        font-size: 14px;
    }

    /* Popup */
    .modal-backdrop {
        position: fixed;
        top: 0;
        left: 0;
        width: 100vw;
        height: 100vh;
        background: rgba(0, 0, 0, 0.8);
        display: flex;
        align-items: center;
        justify-content: center;
        z-index: 9999;
    }

    .modal {
        background: white;
        padding: 2rem;
        border-radius: 12px;
        max-width: 90vw;
        max-height: 90vh;
        overflow: auto;
    }

    .modal img {
        max-width: 100%;
        max-height: 60vh;
        object-fit: cover;
        border-radius: 8px;
    }

    .modal-actions {
        margin-top: 1rem;
        display: flex;
        gap: 1rem;
        justify-content: flex-end;
    }
</style>

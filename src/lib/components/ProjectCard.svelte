<script>
    export let title;
    export let description;
    export let link;
</script>

<div class="card">
    <h3>{title}</h3>
    <p>{description}</p>
    {#if link}
        <a href={link} target="_blank">Voir le projet</a>
    {/if}
</div>

<style>
    .card {
        background: white;
        border-radius: 12px;
        padding: 1.5rem;
        box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        margin: 1rem 0;
        transition:
            transform 0.3s,
            box-shadow 0.3s;
    }
    .card:hover {
        transform: translateY(-5px);
        box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
    }
    .card h3 {
        margin-bottom: 0.5rem;
    }
    .card a {
        display: inline-block;
        margin-top: 0.5rem;
        color: #3b82f6;
        text-decoration: none;
        font-weight: 500;
    }
</style>

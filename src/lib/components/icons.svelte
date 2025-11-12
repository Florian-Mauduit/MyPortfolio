<script>
    import { icons } from "../icons/icons";
    export let name;
    export let selected = false;
    export let className = "";
</script>

{#if icons[name]}
    <svg class="icon {className}" viewBox="0 0 24 24" fill="none" stroke="none">
        {@html icons[name]}
    </svg>
{/if}

<style>
</style>

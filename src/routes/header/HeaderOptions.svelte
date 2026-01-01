<script lang="ts">
    import { cubicOut } from "svelte/easing";
    import { slide } from "svelte/transition";

    let { expanded, options }: { expanded: boolean; options: string[] } = $props();
</script>

{#if expanded}
    <div
        class="options-container"
        transition:slide={{ duration: 200, easing: cubicOut }}
    >
        <ul>
            {#each options as option}
                <li>{option}</li>
            {/each}
        </ul>
    </div>
{/if}

<style>
    .options-container {
        display: flex;
        position: absolute;
        top: 100%;
        left: 0;
        width: 100%;
        padding: 20px;
        box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        background: var(--text-color);
        color: var(--bg-color);
    }

    ul {
        list-style: none;
        margin: 0;
        padding: 0;
        width: 100%;
        display: flex;
        justify-content: space-around;
    }

    li {
        color: var(--bg-color);
        cursor: pointer;
        padding: 10px 20px;
        border-radius: 5px;
    }
</style>

<script lang="ts">
    let {children, ...rest}: { children?: any, [key: string]: any } = $props();
</script>

<div class="text-block" {...rest}>
    {#if children}
        {@render children()}
    {/if}
</div>

<style>
    .text-block {
        flex-direction: column;
        align-items: center;
        justify-content: center;

        height: 25vh;
        width: 25vh;
        display: flex;
        padding: 10px;
        border-radius: 5px;
        flex-shrink: 0;

        color: var(--bg-color);
        font-weight: 400;
        user-select: none;
        text-align: center;

        box-sizing: border-box;
        container-type: size;

        background-color: var(--text-color);
    }
</style>

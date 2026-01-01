<script lang="ts">
    import { onMount } from "svelte";
    import HeaderOptions from "./HeaderOptions.svelte";

    let navElement: HTMLElement | null = null;

    onMount(() => {
        const observer = new ResizeObserver((entries) => {
            for (let entry of entries) {
                document.documentElement.style.setProperty(
                    "--header-height",
                    `${entry.borderBoxSize[0].blockSize}px`
                );
            }
        });

        if (navElement) observer.observe(navElement);
        return () => observer.disconnect();
    });

    let expanded = $state(false);
    let options = $state([""]);
</script>

<div
    bind:this={navElement}
    id="header"
    onmouseleave={() => {
        expanded = false;
    }}
    role="navigation"
    aria-label="Main Navigation"
>
    <div style="display:flex; align-items:center;">
        <div class="logo-block"></div>
        <span style="font-weight: bold; user-select: none;">Matt Bowlby</span>
    </div>
    <div style="display:flex; gap:40px; align-items:center; z-index: 11;">
        <button
            onmouseenter={() => {
                options = ["Work History", "Skills", "Education"];
                expanded = true;
            }}
        >
            Experience
        </button>
        <button
            onmouseenter={() => {
                options = ["Personal Projects", "Academic Projects", "Industry Projects"];
                expanded = true;
            }}
        >
            Projects
        </button>
        <button
            onmouseenter={() => {
                options = ["Awards", "Certifications", "Endorsements"];
                expanded = true;
            }}
        >
            Merits
        </button>
        <button
            onmouseenter={() => {
                options = ["Who I am", "Personal Updates", "Timeline"];
                expanded = true;
            }}
        >
            About Me
        </button>
        <button style="font-weight: bold;" onmouseenter={() => (expanded = false)}>
            Contact
        </button>
    </div>
    <HeaderOptions {expanded} {options} />
</div>

<style>
    #header {
        --bg-gradient-angle: 45deg;

        --background-gradient: repeating-linear-gradient(
            var(--bg-gradient-angle),
            var(--bg-color) calc(-1 * var(--bg-gradient-offset)),
            var(--bg-color) calc(calc(-1 * var(--bg-gradient-offset)) + var(--bg-gradient-width)),
            color-mix(in srgb, var(--bg-color), white 1%)
                calc(calc(-1 * var(--bg-gradient-offset)) + var(--bg-gradient-width)),
            color-mix(in srgb, var(--bg-color), white 1%)
                calc(
                    calc(-1 * var(--bg-gradient-offset)) + var(--bg-gradient-width) +
                        var(--bg-gradient-spacing)
                )
        );

        height: fit-content;
        padding: 20px;
        position: fixed;
        left: 0;
        top: 0;
        right: 0;
        display: flex;
        align-items: center;
        justify-content: space-between;
        z-index: 10;
        background: var(--background-gradient);
        box-shadow: 0 0 20px color-mix(in srgb, var(--bg-color), black 30%);
    }

    button {
        user-select: none;
        background: transparent;
        border: none;
        color: inherit;
        font-family: inherit;
        font-size: 1rem;
        cursor: pointer;
        padding: 5px;
        transition: opacity 0.2s;
    }
    button:last-child {
        background-color: var(--text-color);
        color: var(--bg-color);
        border-radius: 5px;
        padding: 5px 10px;
    }
    button:hover {
        opacity: 0.7;
    }

    .logo-block {
        width: 20px;
        height: 20px;
        background-color: var(--text-color);
        margin-right: 10px;
    }
</style>

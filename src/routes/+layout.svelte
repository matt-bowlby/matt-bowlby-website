<script lang="ts">
    import "../app.css";
    import Header from "./Header.svelte";
    import { Tween } from "svelte/motion";
    import { linear } from "svelte/easing";
    import { onMount } from "svelte";

    const progress = new Tween(0, {
        duration: 1,
        easing: linear,
    });

    async function loop() {
        while (true) {
            await progress.set(1, { duration: 10000 });
            // 2. Instantly reset to 0 without animation
            await progress.set(0, { duration: 0 });
        }
    }

    $effect(() => {
        // Runs only in the browser and reacts to changes in progress.current
        document.documentElement.style.setProperty(
            "--bg-gradient-offset",
            `${progress.current * 60}px`
        );
    });

    onMount(loop);

    let { children } = $props();
</script>

<svelte:head>
    <title>Matt Bowlby - Software Engineer & Web Developer</title>
    <meta
        name="description"
        content="Portfolio website of Matt Bowlby, showcasing experience, projects, and skills in software engineering and web development."
    />
</svelte:head>

<div>
    <Header />

    <main>
        <div class="scroll-container">
            {@render children()}
        </div>
    </main>
</div>

<style>
    /* @import url("https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap"); */

    /* :root {
        --bg-color: #191919;
        --text-color: #fff4df;

        --bg-gradient-angle: 135deg;
        --bg-gradient-width: 20px;
        --bg-gradient-spacing: 40px;
        --bg-gradient-offset: 0px;

        --background-gradient: repeating-linear-gradient(
            var(--bg-gradient-angle),
            var(--bg-color) var(--bg-gradient-offset),
            var(--bg-color) calc(var(--bg-gradient-offset) + var(--bg-gradient-width)),
            color-mix(in srgb, var(--bg-color), white 1%)
                calc(var(--bg-gradient-offset) + var(--bg-gradient-width)),
            color-mix(in srgb, var(--bg-color), white 1%)
                calc(
                    var(--bg-gradient-offset) + var(--bg-gradient-width) +
                        var(--bg-gradient-spacing)
                )
        );

        --header-height: 60px;
    }

    :global(body) {
        margin: 0;
        font-family: "Inter", sans-serif;
        background-color: var(--bg-color);
        background-attachment: local;
        color: var(--text-color);
        box-sizing: border-box;
        overflow: hidden;
    } */

    .scroll-container {
        overflow-y: scroll;
        scroll-snap-type: y mandatory;
        background: var(--background-gradient);
        z-index: -1;
        height: calc(100vh - var(--header-height));
        display: flex;
        flex-direction: column;
        margin-top: calc(var(--header-height));
    }
</style>

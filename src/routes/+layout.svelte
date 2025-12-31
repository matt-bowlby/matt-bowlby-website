<script lang="ts">
    import "../app.css";
    import "./layout.css";

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
            await progress.set(1, { duration: 4000 });
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
            <div style="width: 100%; text-align: center;">
                <span>hi there :)</span>
            </div>
            <div style="position: relative;">
                <div class="border horizontal left"></div>
                <div class="border horizontal right"></div>
                <div class="background"></div>
                <div>
                    {@render children()}
                </div>
            </div>
        </div>
        <div class="border vertical bottom"></div>
    </main>
</div>

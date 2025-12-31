<script lang="ts">
    function calculateYearsSince(dateString: string): number {
        const startDate = new Date(dateString);
        const currentDate = new Date();
        let years = currentDate.getFullYear() - startDate.getFullYear();
        const monthDiff = currentDate.getMonth() - startDate.getMonth();
        if (monthDiff < 0 || (monthDiff === 0 && currentDate.getDate() < startDate.getDate())) {
            years--;
        }
        return years;
    }

    const programmingExperience = calculateYearsSince("2016-02-06");
</script>

<div class="border horizontal left"></div>
<div class="border horizontal right"></div>
<div class="border vertical bottom"></div>
<div class="frame" style="align-items: center; justify-content: flex-end; padding: 20px;">
    <div
        style="
        display: flex;
        justify-content: space-between;
        align-items: flex-end;
        width: 100%;
        height: 25vh;
        margin-bottom: 20px;
        container-type: size;
    "
    >
        <div style="display: flex; height: calc(50% - 10px); width: auto; gap: 20px;">
            <div class="stat-block large"></div>
            <div
                style="display: flex; flex-direction: column; justify-content: space-between; height: 100%;"
            >
                <span class="tagline">Software Engineer.</span>
                <span class="tagline">Web Developer.</span>
                <span class="tagline">
                    Programming <span class="tagline bold">Perfectionist.</span>
                </span>
            </div>
        </div>
        <div style="display: flex; gap: 20px; height: 100%;">
            <div
                style="display: flex; flex-direction: column; align-items: flex-end; gap: 20px; height: 100%;"
            >
                <div class="stat-block small">
                    <span class="stat-number" style="font-size: 35cqh">3</span>
                    <span class="stat-label" style="font-size: 20cqh">job positions</span>
                </div>
                <div class="stat-block wide">
                    <span class="stat-number" style="font-size: 35cqh">6</span>
                    <span class="stat-label" style="font-size: 20cqh"
                        >personal & academic projects</span
                    >
                </div>
            </div>
            <div class="stat-block">
                <span class="stat-number" style="font-size: 35cqh">{programmingExperience}</span>
                <span class="stat-label" style="font-size: 12cqh"
                    >years of programming experience</span
                >
            </div>
        </div>
    </div>
    <svg viewBox="0 0 1394 136" style="width: calc(100% - 20px); height: auto; user-select: none; ">
        <use href="/matt_bowlby.svg#Matt_Bowlby_Logo" />
    </svg>
</div>
<div class="frame"></div>

<style>
    .frame {
        width: 100%;
        height: 100vh;
        display: flex;
        flex-direction: column;
        overflow-y: hidden;
        box-sizing: border-box;
        scroll-snap-align: start;
        scroll-snap-stop: always;
    }
    .border {
        position: fixed;
        pointer-events: none;
    }
    .border.horizontal {
        z-index: -1;
        width: 15%;
        height: 100vh;
        top: 0;
    }
    .border.horizontal.left {
        left: 0;
        background: linear-gradient(
            to right,
            color-mix(in srgb, var(--bg-color), transparent 30%),
            color-mix(in srgb, var(--bg-color), transparent 100%) 100%
        );
    }
    .border.horizontal.right {
        right: 0;
        background: linear-gradient(
            to left,
            color-mix(in srgb, var(--bg-color), transparent 30%),
            color-mix(in srgb, var(--bg-color), transparent 100%) 100%
        );
    }
    .border.vertical {
        z-index: 10;
        width: 100%;
        height: 15vh;
        left: 0;
    }
    .border.vertical.bottom {
        left: 0;
        bottom: 0;
        width: 100%;
        height: 5vh;
        background: linear-gradient(
            to top,
            color-mix(in srgb, var(--bg-color), transparent 50%),
            color-mix(in srgb, var(--bg-color), transparent 100%) 100%
        );
        z-index: 10;
    }

    .stat-block {
        height: 100%;
        aspect-ratio: 1 / 1;
        background-color: var(--text-color);
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        padding: 10px;
        box-sizing: border-box;
        container-type: size;
        border-radius: 5px;
    }

    .stat-block.small {
        height: calc(50% - 10px); /* Adjust for the 20px gap */
    }
    .stat-block.wide {
        height: calc(50% - 10px); /* Adjust for the 20px gap */
        aspect-ratio: 2/1;
        width: auto;
    }

    .stat-number {
        color: var(--bg-color);
        font-weight: 900;
        user-select: none;
        line-height: 1;
    }

    .stat-label {
        color: var(--bg-color);
        font-weight: 400;
        user-select: none;
        text-align: center;
    }
    .tagline {
        font-size: 10cqh;
        font-weight: 400;
        user-select: none;
        white-space: nowrap;
    }
    .tagline.bold {
        font-weight: 900;
    }
</style>

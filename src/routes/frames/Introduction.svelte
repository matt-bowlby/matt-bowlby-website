<script lang="ts">
    import "./frame.css";
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

<div class="frame" style="justify-content: flex-end;">
    <div class="details">
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

<style>
    .details {
        display: flex;
        justify-content: space-between;
        align-items: flex-end;
        width: 100%;
        height: 25vh;
        margin-bottom: 20px;
        container-type: size;
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

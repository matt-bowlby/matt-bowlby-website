<script lang="ts">
    import "./frame.css";
    import TextBlock from "./TextBlock.svelte";

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
    <div id="main-container">
        <div id="tagline-container">
            <div class="tagline-text">Software Engineer.</div>
            <div class="tagline-text">Web Developer.</div>
            <div class="tagline-text">
                Programming <span class="tagline-text bold">Perfectionist.</span>
            </div>
        </div>
        <div id="text-blocks-container">
            <TextBlock>
                <span style="font-size: 35cqh; font-weight: 900">{programmingExperience}</span>
                <span style="font-size: 12cqh">years of programming experience</span>
            </TextBlock>
            <div id="small-text-blocks-container">
                <TextBlock style="height: calc(13vh - 15px); aspect-ratio: 1/1; width: auto;">
                    <span style="font-size: 35cqh; font-weight: 900">3</span>
                    <span style="font-size: 20cqh">job positions</span>
                </TextBlock>
                <TextBlock style="height: calc(13vh - 15px); aspect-ratio: 2/1; width: auto;">
                    <span style="font-size: 35cqh; font-weight: 900">6</span>
                    <span style="font-size: 20cqh">personal & academic projects</span>
                </TextBlock>
            </div>
        </div>
    </div>
    <div id="matt-bowlby-container">
        <svg
            viewBox="0 0 1394 136"
            style="width: calc(100vw - 40px); height: auto; user-select: none; "
        >
            <use href="/matt_bowlby.svg#Matt_Bowlby_Name" />
        </svg>
    </div>
</div>

<style>
    #matt-bowlby-container {
        height: fit-content;
        width: fit-content;
        user-select: none;
        flex-shrink: 0;
    }
    #main-container {
        height: fit-content;
        width: 100%;
        margin-bottom: 20px;
        display: flex;
        justify-content: space-between;
        align-items: flex-end;
    }
    #text-blocks-container {
        display: flex;
        gap: 20px;
        align-items: center;
        flex-direction: row-reverse;
    }
    #small-text-blocks-container {
        display: flex;
        flex-direction: column;
        align-items: flex-end;
        gap: 20px;
    }
    #tagline-container {
        height: 100%;
        display: flex;
        flex-direction: column;
        justify-content: flex-end;
        container-type: size;
    }

    .tagline-text {
        font-size: 10cqh;
        font-weight: 400;
        user-select: none;
        white-space: nowrap;
    }

    .tagline-text.bold {
        font-weight: 900;
    }
</style>

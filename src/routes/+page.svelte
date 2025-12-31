<script lang="ts">
    import Introduction from "./frames/Introduction.svelte";

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

<Introduction />
<Introduction />


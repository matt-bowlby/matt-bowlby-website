<script lang="ts">

	let { children } = $props();
</script>

<svelte:head>
</svelte:head>

{@render children()}

<style>
	:global(body) {
		margin: 0;
		font-family: system-ui, sans-serif;
		--bg-color: #191919;
		--text-color: #FFF4DF;
		background-color: var(--bg-color);
		color: var(--text-color);
	}
</style>
<script lang="ts">
	export let filled: number;
</script>

{#if filled === 1}
	<div class="filledSegment" />
{:else}
	<div class="emptySegment" />
{/if}

<style>
	div {
		min-width: 10px;
		min-height: 10px;
		border-radius: 2px;
	}
	.filledSegment {
		background-color: red;
	}
	.emptySegment {
		background-color: white;
	}
</style>

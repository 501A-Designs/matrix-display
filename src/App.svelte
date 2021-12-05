<script lang="ts">
	import PixelDisplay from "./lib/PixelDisplay.svelte";
	let ascii: string = "";
	let inputAsciiArray: any = [];
	const asciiArrayFunction = () => {
		inputAsciiArray = ascii.toString().split("");
		console.log(inputAsciiArray);
	};
</script>

<main>
	<div>
		<h1>matrix-display</h1>
		<h2><a href="https://501a.netlify.app">made with svelte by 501A</a></h2>
		<p>
			currently only supports upper case ascii characters. If you open the console you can
			see the full binary array for each number.
		</p>
		<input type="text" bind:value={ascii} on:input={asciiArrayFunction} />
	</div>
	<hr />

	<div class="flex">
		{#each inputAsciiArray as asciiChar}
			<PixelDisplay asciiType={asciiChar} />
		{/each}
	</div>
</main>

<style>
	h1,
	h2 {
		margin: 0;
		padding: 0;
	}
	.flex {
		display: flex;
		gap: 5px;
	}
</style>

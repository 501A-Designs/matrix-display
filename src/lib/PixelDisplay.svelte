<script lang="ts">
	// import App from "../App.svelte";
	import Pixel from "./Pixel.svelte";
	import { asciiBin } from "../bin";

	export let asciiType: any;
	const asciiArray: any = [
		"A",
		"B",
		"C",
		"D",
		"E",
		"F",
		"G",
		"H",
		"I",
		"J",
		"K",
		"L",
		"M",
		"N",
		"O",
		"P",
		"Q",
		"R",
		"S",
		"T",
		"U",
		"V",
		"W",
		"X",
		"Y",
		"Z",
	];
	const arrayIndexValue = asciiArray.findIndex(
		(element) => element === asciiType
	);

	let asciiChar = asciiBin[arrayIndexValue][asciiType];

	console.log(asciiChar);
	let fullAsciiVerticalArray = [];
	for (let i = 0; i < asciiChar.length; i++) {
		let asciiRow = asciiChar[i];
		let asciiVerticalArray = [];
		asciiVerticalArray = asciiRow
			.toString()
			.split("")
			.map((iNum) => parseInt(iNum, 10));
		fullAsciiVerticalArray.push(asciiVerticalArray);
	}
</script>

<div class="display">
	{#each [0, 1, 2, 3, 4, 5, 6, 7] as j}
		{#each fullAsciiVerticalArray[j] as i}
			<Pixel filled={i} />
		{/each}
	{/each}
</div>

<style>
	.display {
		width: 90px;
		display: grid;
		grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr;
		gap: 2px;
		margin-right: 5px;
		border-radius: 2px;
	}
</style>

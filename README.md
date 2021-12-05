# matrix-display

A matrix display that operates through a 8-bit binary code powered by [Svelte](https://svelte.dev).

## ASCII letters as displayed

The user input is passed down as a prop to the `<PixelDisplay/>` component and its value is used to index through the `asciiArray` list (a list of letters corresponding to the binary array in `bin.ts`). The binary data for each ascii letter is stored in `bin.ts` as an array object array string. The index recived from the `asciiArray` is used to navigate through `bin.ts`. Using the same method used in the seven segment display, the string containing the binary data is split by its indivisual character and are fed in conditionally rendered svelte components via sveltes `{#each}` block.

By having the `asciiArray` as a indexing ruler for navigating through `bin.ts` more letters & symbols can be added as the indexing number does not tied to the outputted value. A simplified version of this can be seen [here](https://github.com/501A-Designs/seven-segment-display) with the seven-segment-display as an example.

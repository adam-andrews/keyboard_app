<script>
	let typer = '';
	const sentence = 'Hello my name is adam';
</script>

{#each sentence as letter, wordIndex}
	<span class:selected={typer[wordIndex] === letter}> {letter} </span>
{/each}
<input placeholder="Hello" bind:value={typer} />

<div>This is where the keyboard will be</div>

<style>
	.selected {
		font-size: 5rem;
	}
</style>

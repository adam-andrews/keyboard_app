<script>
	let message = 'This is the message';
	import { popularEnglishWords } from '../words.js';

	let cursor = 1;
	function handleChange(e) {
		if (e.data === ' ') {
			message += ' ' + popularEnglishWords[Math.floor(Math.random() * 100)];
		}
		if (e.data === message[cursor]) {
			cursor += 1;
		} else {
			alert('incorrect letter');
		}
	}
</script>

<div class="container">
	<div>
		{#each message as letter, wordIndex}
			{#if wordIndex === cursor}
				<span class="selected">{letter}</span>
			{:else}
				<span class="">{letter}</span>
			{/if}
		{/each}
	</div>
	<input on:input={(e) => handleChange(e)} />
</div>

<!-- <script>
	let typer = '';
	const sentence = 'Hello my name is adam';
</script>

<div class="container">
	<div>
		{#each sentence as letter, wordIndex}
			<span class:selected={typer[wordIndex] === letter.toLowerCase()}
				>{letter}</span
			>
		{/each}
	</div>

	<input placeholder="Hello" bind:value={typer} />

	<div>This is where the keyboard will be</div>
</div>

 -->

<style>
	.container {
		height: 100vh;
		display: flex;
		background: #dd7575;
		justify-content: center;
		align-content: center;
		flex-direction: column;
		font-size: 5rem;
	}
	.selected {
		font-size: 5rem;
		color: gray;
		text-decoration: underline;
		text-decoration-color: red;
	}
</style>

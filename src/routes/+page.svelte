<script>
	import { text } from '@sveltejs/kit';
	import Level from './level.svelte';
	let range = (n) => [...Array(n).keys()];
	let zestLevel = $state(0);
	let textInput = $state('');
	function determineZestLevel() {
		if (textInput.trim()) {
            let loop = startAnimateZest();

			puter.ai.chat(`Hello, you are being used in an API and are to exclusively respond with a number, on a scale of 1 to 10 how zesty/subtly gay is this message "${textInput.trim()}" `).then((response) => {
                clearInterval(loop);
                animateZest(response);
            });
		}
	}

	function clamp(a, b, c) {
		if (b < a) {
			return a;
		} else if (b > c) {
			return c;
		}
		return b;
	}
	let increment = 1;

	function animateZest(goal) {
        console.log(goal.message.content);
        console.log(goal);
        goal = goal.message.content;
        goal = parseInt(goal.replace(/\D/g,''));
		let loop = setInterval(() => {
			zestLevel += increment;
			if (zestLevel > 10 || zestLevel < 0) {
				increment *= -1;
			}
			zestLevel = clamp(0, zestLevel, 10);
			console.log(zestLevel);
		}, 10);
		setTimeout(() => {
		    clearInterval(loop);
		    zestLevel = goal;
		}, 750);
	}
	function startAnimateZest(goal) {
		let loop = setInterval(() => {
			zestLevel += increment;
			if (zestLevel > 10 || zestLevel < 0) {
				increment *= -1;
			}
			zestLevel = clamp(0, zestLevel, 10);
			console.log(zestLevel);
		}, 10);
        return loop;
	}
	// animateZest("8");
</script>

<svelte:head>
	<script src="https://js.puter.com/v2/"></script>
    <title>Zest-Meter</title>
</svelte:head>

<div class="body">
	<div class="container">
		<form action="">
            <div>
                <h1 style="border: none; margin-bottom: none;">Zest Meter :D</h1>
                <p>My dumbest project yet lol</p>
            </div>
			<textarea type="text" name="" id="" placeholder="Write Anything..." bind:value={textInput}
			></textarea>
			<button type="submit" onclick={determineZestLevel}>Analyse</button>
		</form>
		<div class="meter">
			{#each range(zestLevel) as level}
				<Level {level} />
			{/each}
		</div>
	</div>
</div>

<style>
	:global(*) {
		font-family: Arial, sans-serif;
		color: #413c58;
		border-radius: 0.6em;
	}
	.meter {
		display: flex;
		gap: 0.6em;
		flex-direction: column-reverse;
		justify-content: flex-start;
		height: 27em;
		background-color: #f2e7c952;
		padding: 1em;
		width: 15em;
	}

	.container {
		display: flex;
		width: 60vw;
		justify-content: space-between;
		align-items: center;
		height: 80vh;
		background-color: #a3c4bc;
		padding: 2em;
		padding-left: 3em;
		padding-right: 3em;
		border-radius: 2em;
		-webkit-box-shadow: 0px 0px 12px 1px #413c58;
		box-shadow: 0px 0px 12px 1px #413c58;
	}

	.body {
		width: 100vw;
		height: 100vh;
		display: flex;
		justify-content: center;
		align-items: center;
		background-color: #bfd7b5;
		border: none;
		border-radius: 0px;
		margin: 0px;
	}

	form {
		display: flex;
		flex-direction: column;
		height: 100%;
		gap: 0em;
		width: 80%;
	}

	textarea {
		width: 80%;
		height: 70%;
		background-color: #f2e7c9;
		padding: 1em;
		resize: none;
		-webkit-box-shadow: 0px 0px 5px 1px rgba(0, 0, 0, 0.54);
		box-shadow: 0px 0px 5px 1px rgba(0, 0, 0, 0.54);
	}

	button {
		margin-top: 2.5em;
		width: 6.4em;
		height: 2.3em;
		background-color: #f2e7c9;
		font-weight: bold;
		border-width: 0.2em;
		font-size: large;
	}
</style>

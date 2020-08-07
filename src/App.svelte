<script>
	let guessNumber = Math.floor(Math.random()*100)+1;
	console.log(guessNumber)
	let guessNumArray = [];
	let userGuess = ""
	let low = 1;
	let high = 100;
	let attempts = 5;
	let result = "NOT YET STARTED!"
	let restartGame = () =>{
	 guessNumber = Math.floor(Math.random()*100)+1;
	 guessNumArray = [];
	 console.log(guessNumber)
	 userGuess;
	 low = 1;
	 high = 100;
	 attempts = 5;
	 result = "NOT YET STARTED!"
	}
	let takeAction = ()=>{
		guessNumArray.push(userGuess);
		guessNumArray = guessNumArray;
		attempts--;
		if(attempts > 0)
		{
			if(userGuess > guessNumber){
					if (userGuess < high) high = userGuess;
				result = `Your guess is high! Guess between ${low} and ${high}`;
			}
			else if(userGuess < guessNumber){
				if (userGuess > low ) low = userGuess;
				result = `Your guess is low! Guess between ${low} and ${high}`;
			}
			else if (userGuess === guessNumber){
				result = "You won the game! - Play a new game!"
			}
			else{
				result = "Some error!"
			}
		}
		else if (attempts === 0){
			if (userGuess === guessNumber) {
				result = "You won the game! - Play a new game!"
			}
			else{
				result = "You lost! Restart the game!"
			}
		}
		else{
			result = "You lost! Restart the game!"
		}
		userGuess = '';
	}
</script>
<main>
<button on:click={restartGame}>
	New game
</button>
{#if attempts > 0}
	<h5>
		Remaining attempts : {attempts}
	</h5>
	<input type="number" min="0" bind:value={userGuess}/>
	<button on:click={takeAction}>Guess</button>
{/if}
<hr>
<h4>
	{result}
</h4>
<ul>
	{#each guessNumArray as guessValues}
	   <li>{guessValues}</li>
	{:else}
	   <li>
			 guess a value man!
	   </li>
	{/each}
</ul>
</main>
<style>
main{
	text-align: center;
}
</style>
<script>
	let makeJoke = async ()=>{
		let result = await fetch("https://breaking-bad-quotes.herokuapp.com/v1/quotes/100");
		let jokes = await result.json();
				console.log(jokes)
		return jokes;
	}
</script>

<main>
	<button>Joke pls</button>
	<hr/>
	<hr/>
	{#await makeJoke() then quotes}
	{#each quotes as quote}
  <h1>
		{quote.quote}
	</h1>
	<h2>
		{quote.author}
	</h2>
	<hr/>
	
	{/each}
	{/await}
</main>

<style>
	h1{
		color: lightgreen;
	}
	h2{
		color : #0055aa;
	}
</style>

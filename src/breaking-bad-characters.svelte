<script>
	let url = "https://www.breakingbadapi.com/api/characters";
	async function callChar(){
		let res =  await fetch(url);
		let characters = await res.json();
		return characters;
	}
</script>

{#await callChar() then characters}
<div class="grid">
	{#each characters as char}
	   <div class="char-card">
			  <h2>{char.name}</h2>
			  <img width="200" src={char.img} alt={char.char_id}/>
	  </div>
	{/each}
</div> 
{/await}

<style>
	.grid{
		display: grid;
		gap: 1rem;
		grid-template-columns: repeat(auto-fit, minmax(200px,1fr))
	}
	.char-card h2{
		text-align: center;
	}
</style>

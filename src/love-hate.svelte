<script>
	let sentence = "";
</script>
<h5>
	Never propose me! 🌹
</h5>
<input type="text" bind:value={sentence}/>
<hr/>
{#each sentence.split(" ") as value}
	{#if value.includes("love")}
		<strike>
			{value} 
		</strike> ❌ - better hate me!
  {:else if value.toLowerCase() === "hate"}
		<strong> {value} ✅</strong>
	{:else}
		<p>
			{value}
		</p>
	{/if}
{/each}

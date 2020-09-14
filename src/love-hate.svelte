<script>
	let sentence = "";
</script>
<h5>
	Never propose me! ❌
</h5>
<input type="text" bind:value={sentence}/>
<hr/>
{#each sentence.split(" ") as value}
	{#if value.toLowerCase().includes("love")}
		<p>
			<strike>
			{value} 
		</strike> ❌ - better <strong>hate</strong> me! </p>
  {:else if value.toLowerCase() === "hate"}
<p>
	<strong> {value} ✅</strong>
</p>
	{:else}
		<p>
			{value}
		</p>
	{/if}
{/each}

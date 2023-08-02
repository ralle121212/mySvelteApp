<script>
	let airdropInput = "";

	let categories = [
	{id: 1, category: "Airdrop"}
	{id: 2, category: "Mine-2-Earn"},
	{id: 3, category: "Task-2-Earn"},
	{id: 4, category: "Testnet Incentive"}
];

</script>

<select bind:value={airdropInput}>
	{#each categories as category}
	<option value={category}>
		{category.category}
	</option>
	{/each}
</select>
<p>{categories.airdropInput}</p>
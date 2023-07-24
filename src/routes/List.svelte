<script lang="ts">

import { createEventDispatcher, setContext } from 'svelte';

// Define the context
const dispatch = createEventDispatcher();
	
	let newAirdrop = "";
	let category = "";
	let categories = ["Mine-2-Earn", "Wallets", "Task-2-Earn", "Airdrop", 
	"Testnet Incentives", "Play-2-Earn", "Other Ways"]
	let airdropList: any[] = [];
	
	
	let add = () => {
    if (newAirdrop !== "" && category !== "") {
      // Emit an event with the new data to be added
      dispatch('addAirdrop', {
        task: newAirdrop,
        category: category,
      });
			
	newAirdrop = "";
	category = "";
	}
};	
	</script>
s
<div class="list">

	<!--List in Form -mode-->
	<form on:submit|preventDefault={add}>
		<textarea bind:value={newAirdrop} placeholder="Enter some airdrop to website"></textarea />
		<select bind:value={category} placeholder="Enter Category">
		<option value="">Choose a Category</option>
		
		{#each categories as item}
		<option value={item}>{item}</option>
		{/each}
		</select>
		
		<button class="addingAirdrop" on:click={add}><span>+</span></button>
	</form>
</div>

<section class="todos">
{#each airdropList as item, index}
<span class="todo_text"> {item.task}</span>
<div class="todo_buttons"></div>
{/each}
</section>

<style>
.list {
	display: flex;
	flex-direction: column;
	align-items: center;
}
</style>

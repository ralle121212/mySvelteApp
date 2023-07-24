<script>
 import List from "../List.svelte";

 /**
	 * @type {any[]}
	 */
 let airdropItems = [];

const handleAddAirdrop = (/** @type {{ detail: any; }} */ event) => {
    airdropItems.push(event.detail);
    console.log(airdropItems);
};

</script>

    <div class="body">
        <List on:addAirdrop={handleAddAirdrop} />
        <ul>
            {#each airdropItems as item}
            <li>{item.task} - {item.category}</li>
            {/each}
        </ul>
        
    </div>

<style>
    .body {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

</style>
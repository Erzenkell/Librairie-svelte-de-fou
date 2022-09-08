<script>


    let todolist = [
        {text: 'First post', status: true},
        {text: 'Second post', status: true},
        {text: 'Third post', status: false}
    ];

    let newItem = '';

    function addToList() {
		todolist = [...todolist, {text: newItem, status: false}];
		newItem = '';
	}
	
	function removeFromList(index) {
		todolist.splice(index, 1)
		todolist = todolist;
    }
    let i = 0
</script>

<section class='todo text-justify m-auto w-fit'>

    <input id="large-input" bind:value={newItem} placeholder="New item" type="text">
    <button class="text-green-700 hover:text-white border border-green-700 hover:bg-green-800 focus:ring-4 focus:outline-none focus:ring-green-300 font-medium rounded-lg text-sm px-3 py-1.5 text-center mr-2 mb-2 dark:border-green-500 dark:text-green-500 dark:hover:text-white dark:hover:bg-green-600 dark:focus:ring-green-800" on:click={addToList}>Add</button>
    <h3>You have {todolist.length} items in your list, 
    {#each todolist as item, index}
    {item.status == true ? i = i + 1 : ''}
    <!-- {#if item.status == true, i++ }
    {item.status.length}
    {/if} -->
    {/each} 
    {i}
    are completed.</h3>
    {#each todolist as item, index}


    <div class='my-4'>
	<input bind:checked={item.status} type="checkbox">
	<span class:checked={item.status}>{item.text}</span>
    <button class='text-red-700 hover:text-white border border-red-700 hover:bg-red-800 focus:ring-4 focus:outline-none focus:ring-red-300 font-medium rounded-lg text-sm px-3 py-1.5 text-center mr-2 mb-2 dark:border-red-500 dark:text-red-500 dark:hover:text-white dark:hover:bg-red-600 dark:focus:ring-red-900' on:click={() => removeFromList(index)}>Remove</button>
    </div>
    {/each} 

</section>

<style> 
	.checked {
        text-decoration: line-through;
    }
</style> 
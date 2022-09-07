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

</script>

<section class='todo text-justify m-auto w-fit'>

    <input bind:value={newItem} placeholder="New item" type="text">
    <button on:click={addToList}>Add</button>
    {#each todolist as item, index}

    <div class='my-4'>
	<input bind:checked={item.status} type="checkbox">
	<span class:checked={item.status}>{item.text}</span>
    <span on:click={() => removeFromList(index)}>❌</span>
    </div>
    {/each} 

</section>
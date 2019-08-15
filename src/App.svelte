<script>
    let firstname = 'Theresa';
	let name = '';

		let items = [
    		{ id: 1, name: "Milk", done: false },
    		{ id: 2, name: "Bread", done: true },
    		{ id: 3, name: "Eggs", done: false }
    	];

    	const remove = item => {
    		items = items.filter(i => i !== item);
    	};


          const addItem = () => {
            items = [
              ...items,
              { id: Math.random(), name, done: false }
            ];
            name = "";
          };
</script>

<h1>Hello {firstname}!</h1>

	<h1>Things to Buy</h1>

	<form on:submit|preventDefault={addItem}>
      <label for="name">Add an item</label>
      <input id="name" type="text" bind:value={name} />
    </form>

	<ul>
		{#each items as item}
		<input type="checkbox" bind:checked={item.done} />
		    {item.name}
		<!--<span class:done={item.done}>{item.name}</span>-->
		    <button on:click={()=> remove(item)}>
		        ❌
		    </button><br/>
		{/each}
	</ul>
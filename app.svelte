<head>
	<link rel="stylesheet" type="text/css" href="https://cdnjs.cloudflare.com/ajax/libs/skeleton/2.0.4/skeleton.css">
</head>

<script>
	//@STRING[] all possible inputs
	let inputs = [''];

	//@FUNCTION delete element at index i
	const deleteInput = (i) => {
		inputs.splice(i,1); //splice 1 element at index i
		inputs = inputs;    //force reactivity
	}

	//@FUNCTION add an empty string {
	const addInput = () => {
		inputs.push(''); // append empty string
		inputs = inputs; // force reactivity
	}
</script>

<div style="width: 100%; display: flex; text-align: center">
	<div style="margin: auto">
		<h1>Value Array</h1>
		{#each inputs as value, i}
			<div>
				<!-- binds value of input to specific index in array -->
				<input type="text" bind:value placeholder="Answer">
				<button style="background-color: red; color: white;" onclick={() => deleteInput(i)}>DELETE</button>
			</div>
		{/each}
		<button style="background-color: blue; color: white" onclick={addInput}>Add Element</button>
	</div>
</div>

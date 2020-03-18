<svelte:head>
	<title>create</title>
</svelte:head>

<script>
	let questions = [
		{ id: 1, text: `Costco` },
		{ id: 2, text: `Safeway` },
		{ id: 3, text: `Trader Joes` }
	];

	let selected;

	let answer = '';

	function handleSubmit() {
		alert(`answered question ${selected.id} (${selected.text}) with "${answer}"`);
    }
    let quantity = 0;
	let product = ['Nothing'];

	let menu = [
		'Face Masks',
		'Wipes',
        'Kleenex'
	];

	function join(product) {
		if (product.length === 1) return product[0];
		return `${product.slice(0, -1).join(', ')} and ${product[product.length - 1]}`;
	}
</script>

<style>
	input { display: block; width: 500px; max-width: 100%; }
</style>

<h2>New Post</h2>
<h3>Select Location</h3>
<h3>Comments</h3>

<form on:submit|preventDefault={handleSubmit}>
	<select value={selected} on:change="{() => answer = ''}">
		{#each questions as question}
			<option value={question}>
				{question.text}
			</option>
		{/each}
	</select>

	<input bind:value={answer}>

	<button disabled={!answer} type=submit>
		Submit
	</button>
</form>

<h2>Size</h2>

<label>
	<input type=radio bind:group={quantity} value={1}>
	One scoop
</label>

<label>
	<input type=radio bind:group={quantity} value={2}>
	Two quantity
</label>

<label>
	<input type=radio bind:group={quantity} value={3}>
	Three quantity
</label>

<h2>Product</h2>

{#each menu as flavour}
	<label>
		<input type=checkbox bind:group={product} value={flavour}>
		{flavour}
	</label>
{/each}

{#if product.length === 0}
	<p>Please select at least one flavour</p>
{:else if product.length > quantity}
	<p>Can't order more product than quantity!</p>
{:else}
	<p>
		You ordered {quantity} {quantity === 1 ? 'scoop' : 'quantity'}
		of {join(product)}
	</p>
{/if}

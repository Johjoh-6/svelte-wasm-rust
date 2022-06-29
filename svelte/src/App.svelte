<script>
	export let bindings;
	let result = 0;

	const add = (e) => {
		const form = new FormData(e.target);
		const data = {};
    	for (let field of form) {
     		const [key, value] = field;
      		data[key] = value;
    	}
		result = bindings.add(data.a, data.b);
		return result;
	}
</script>

<main>
	<h1>Add a + b.</h1>
	<form on:submit|preventDefault={add}>
		<label for="a"><input type="number" name="a" id="a" value="0"></label>
		<label for="b"><input type="number" name="b" id="b" value="0"></label>
		<input type="submit" >
	</form>
	<p>{result}</p>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}


	
</style>
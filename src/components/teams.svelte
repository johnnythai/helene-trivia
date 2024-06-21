<script lang='ts'>
	import { writable } from 'svelte/store';

	const teams = writable([]);
	console.log($teams);
</script>

<form>
	<label for="nameInput">Enter a Name:</label>
        <input type="text" id="nameInput" name="name" required>
        <button type="submit">Add Name</button>
</form>

<style>
	
</style>

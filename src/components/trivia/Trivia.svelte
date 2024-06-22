<script lang='ts'>
	// import Scoreboard from "./Scoreboard.svelte";
	// import { writable } from "svelte/store";

	import { questions } from "$lib/questions";
	import Question from "./Question.svelte";

</script>

<div class="trivia">
	<!-- <Scoreboard /> -->
	<Question />

</div>

<style>
	.trivia {
		display: flex;
		justify-content: center; /* Center horizontally */
		align-items: center;    /* Center vertically */
		width: 100vw; 
	}
</style>

<script lang='ts'>
	import { teams } from '$lib/store'

</script>

<div class="scoreboard">
	<div class="team">
		{teams}
	</div>
	
</div>

<style>
	.scoreboard {
		display: inline-flex;
		align-items: center;
		justify-content: center; /* Center content inside the scoreboard if needed */
		padding: 20px;           /* Optional padding for better visualization */
		border: 2px solid black; /* Optional border for better visualization */
		background-color: lightgrey;
	}
</style>

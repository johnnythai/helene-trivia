<!-- select team,  -->
<!-- create new team,  -->
<!-- remove team  -->
<!-- add player to selected team,  -->
<!-- remove player from selected team,  -->

<script lang='ts'>
	import { teams } from '$lib/store'

	const addTeam = (event: Event) => {
		const team: string[] = [];

		teams.update(currentTeams => {
			currentTeams.push(team);
			console.log(currentTeams);
			return currentTeams;
		});
	};
</script>

<button on:click|preventDefault={addTeam}>Create team</button>

<style>
	
</style>

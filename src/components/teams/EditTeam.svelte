<script lang='ts'>
	import { teams } from '$lib/store';
	import CreateTeam from './CreateTeam.svelte';

	interface Player {
		name: string;
		team: number;
	};

	const removePlayer = (event: Event) => {
		const formData = new FormData(event.target as HTMLFormElement);
		const player: Player = {
			name: formData.get('name') as string,
			team: parseInt(formData.get('team') as string, 10) 
		};
		
		teams.update(currentTeams =>{
			if (!currentTeams[player.team-1]) {
				alert('Invalid team number.');
				return currentTeams;
			}

			const updatedTeam = currentTeams[player.team-1].filter(name => player.name == name);
			currentTeams[player.team-1] = updatedTeam;

			return currentTeams;
		});
	};

	const addPlayer = (event: Event) => {
		const formData = new FormData(event.target as HTMLFormElement);
		const player: Player = {
			name: formData.get('name') as string,
			team: parseInt(formData.get('team') as string, 10) 
		};
		
		teams.update(currentTeams =>{
			if (!currentTeams[player.team-1]) {
				alert('Invalid team number.');
				return currentTeams;
			}
			currentTeams[player.team-1].push(player.name);
			return currentTeams;
		});
	};
</script>

<form on:submit|preventDefault={addPlayer}>
	<label for="name">Enter Name:</label>
        <input type="text" id="name" name="name" required>
	<br>
	<label for="team">Team Number:</label>
        <input type="text" id="team" name="team" required>
        <button type="submit" id="add">Add</button>
</form>

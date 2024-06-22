<script lang='ts'>
	import { teams } from '$lib/store'
	import { onDestroy } from 'svelte';
	import CreateTeam from './CreateTeam.svelte';

	let teamsList: string[][] = []

	const unsubscribe = teams.subscribe(values =>{
		teamsList = values;
		console.log('teamsList: ', teamsList)
	});

	onDestroy(() => {
		unsubscribe();
	});
</script>

{#each teamsList as team, i}
	<li>Team {i+1}: {team}</li>	
{/each}
<CreateTeam />

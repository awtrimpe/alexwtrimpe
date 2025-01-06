<script lang="ts">
	import Loves from "../../images/loves-rewards.svelte";
	const stations = [
		{
			name: "BP",
			code: "2416305297550713069",
		},
		{
			name: "Marathon",
			code: "11-Phone Number",
		},
		{
			name: "Shell",
			code: "Phone Number",
		},
		{
			name: "Speedway",
			code: "ALT ID - 432446359648",
		},
		{
			name: "Pilot Flying J",
			code: "9031 2164 9603 95",
		},
		{
			name: "Mobil",
			code: "Phone Number",
		},
		{
			name: "Loves",
			image: Loves,
		},
	].sort((a, b) => (a.name > b.name ? 1 : -1));
</script>

<table>
	<tr>
		<th>Name</th>
		<th>Code</th>
	</tr>
	{#each stations as station}
		<tr>
			<td>{station.name}</td>
			<td>
				{#if station.code}
					{station.code}
				{/if}
				{#if station.image}
					<svelte:component this={station.image}></svelte:component>
				{/if}
			</td>
		</tr>
	{/each}
</table>

<style>
	table {
		margin: auto;
		border-collapse: collapse;
		width: 100%;
	}

	td,
	th {
		padding: 1em 2em;
	}

	td {
		border: none;
	}

	th {
		background-color: black;
		color: white;
	}

	tr:nth-child(odd) {
		background-color: var(--outer-space);
	}
</style>

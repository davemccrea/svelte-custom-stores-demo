<script>
	import DogPopup from "./DogPopup.svelte"
	export let name
	export let state
</script>

<style>
	div {
		height: 200;
		width: calc(100% - 40px);
		background: cadetblue;
		color: #eee;
		font-weight: 500;
		font-size: 20px;
		text-transform: uppercase;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 20px;
	}
	:global(.buttons) {
		display: flex;
		flex-direction: row;
	}
	:global(.buttons) > button:last-of-type {
		margin-left: 10px;
	}
</style>

<div>
	<p>Controlled from {name}</p>
	<p>
		Current:
		<strong>{state ? 'VISIBLE' : 'HIDDEN'}</strong>
	</p>
	<slot />
</div>

{#each [1, 2] as d (d)}
	<DogPopup idx={d} />
{/each}

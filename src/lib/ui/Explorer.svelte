<script>
	import { web3 } from '$lib/stores/web3'
</script>

<template lang="pug">
	
	+if('$web3')
		.data
			+each('Object.entries($web3) as [key, value]')
				.kv
					p.k {key}
					pre.v {value ? Object.keys(value) : null}

</template>

<style lang="scss">
	.data {
		display: flex;
		flex-direction: column;
		gap: 1rem;

		width: 800px;
		padding: 1rem;
		margin: auto;
		margin-top: 2rem;

		font-size: 14px;

		background: var(--light-c);
		border-radius: 5px;
	}
	.kv {
		display: flex;
		flex-direction: row;
		flex-grow: 1;

		width: 100%;
	}
	.k,
	.v {
		width: 100%;
		padding: 0.5rem;

		font-weight: bold;

		border: 1px solid var(--light-d);
	}
	.k {
		width: 250px;

		background: var(--light-c);
		color: var(--dark-b);
	}
	.v {
		font-size: 12px;
		font-family: 'fira mono';

		border-left: none;
	}
	*::-webkit-scrollbar {
		width: 0;
		display: none;
	}
</style>

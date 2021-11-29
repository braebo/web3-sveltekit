<script context="module">
	export const ssr = false
</script>

<script lang="ts">
	import Explorer from '$lib/ui/Explorer.svelte'
	import { web3 } from '$lib/stores/web3'
	import { onMount } from 'svelte'

	onMount(async () => {
		const Web3 = await import('web3/dist/web3.min.js')
		$web3 = new Web3.default()

		console.log($web3)
	})
</script>

<template lang="pug">

	h1(class:$web3) Web3 {$web3 ? 'Connected' : 'Not Connected'}

	Explorer

</template>

<style>
	h1 {
		padding-top: 5rem;

		font-size: 2rem;
		font-weight: bold;
		text-align: center;
	}

	.\$web3 {
		color: rgb(48, 207, 109);
	}
</style>

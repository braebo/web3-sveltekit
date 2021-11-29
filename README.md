An example demonstrating Web3.js in sveltekit.

Basically, you need to dynamically import it:

```js
import { onMount } from 'svelte'

let web3

onMount(async () => {
	const Web3 = await import('web3/dist/web3.min.js')
	web3 = new Web3.default()

	console.log(web3)
})
```

if you get `"require" is not defined`, just add this to your `svelte.config.js`:

```js
...
	vite: {
		define: {
			'process.env': process.env
		}
	}
```

made with [frackit](https://github.com/fractalhq/frackit)

<script>
	import { beforeNavigate } from '$app/navigation';
	import Header from '$lib/header/Header.svelte';
	import '../app.css';

	beforeNavigate((args) => {
		
		console.log(JSON.stringify(args));
		// sveltejs-kit-templat…201&v=a88a86d2:1536 Uncaught (in promise) Error: The navigation shape changed - from.toJSON should now be from.url.toJSON

		console.log('args.from', args.from);
		console.log('args.to', args.to);
		console.log('args.type', args.type);
	})
</script>

<Header />

<main>
	<slot />
</main>

<footer>
	<p>visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to learn SvelteKit</p>
</footer>

<style>
	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 1rem;
		width: 100%;
		max-width: 1024px;
		margin: 0 auto;
		box-sizing: border-box;
	}

	footer {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 40px;
	}

	footer a {
		font-weight: bold;
	}

	@media (min-width: 480px) {
		footer {
			padding: 40px 0;
		}
	}
</style>

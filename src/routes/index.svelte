<script context="module">
	export async function load({ fetch }) {
		const url = 'https://jsonplaceholder.typicode.com/posts';
		const response = await fetch(url);

		return {
			status: 200,
			props: {
				posts: response.ok && (await response.json())
			}
		};
	}
</script>

<script>
	export let posts = '';
</script>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
<p>{JSON.stringify(posts)}</p>

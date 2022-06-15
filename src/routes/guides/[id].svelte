<script lang="ts" context="module">
	import type { LoadEvent } from '@sveltejs/kit';
	import type { Guide } from './[id].json';

	// /** @type {import('@sveltejs/kit').Load} */
	export async function load({ fetch, params }: LoadEvent) {
		// await new Promise((resolve) => setTimeout(resolve, 1000));
		const id: string = params.id;
		// const res = await fetch(`https://jsonplaceholder.typicode.com/posts/${id}`);
		const res = await fetch(`/guides/${id}.json`);
		const { guide } = await res.json();

		if (res.ok) {
			return {
				props: {
					guide
				}
			};
		}

		return {
			// status: res.status,
			// error: new Error('No guide found')
			status: 301,
			redirect: '/guides'
		};
	}
</script>

<script lang="ts">
	export let guide: Guide;
</script>

<div class="guide">
	<h2>{guide.title}</h2>
	<p>{guide.body}</p>
</div>

<style>
	.guide {
		/* margin-top: 40px; */
		padding: 10px;
		border: 1px dotted rgba(255, 255, 255, 0.2);
	}
</style>

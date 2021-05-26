<script>
	import { components } from '@roxi/routify'
	const languagesFolder = $components.find((node) => node.path === '/languages')
	const languages = languagesFolder.children
</script>

{#each languages as language}
	<article>
		{#await language.component then language}
			<svelte:component this={language} />
		{/await}
	</article>
{/each}

<style>
	article:not(:first-of-type) {
		margin: 96px 0;
	}
	article {
		padding: 56px 64px;
		box-shadow: 0 0 16px rgba(0, 0, 0, 0.2);
	}
</style>

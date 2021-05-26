<script>
	import { components } from '@roxi/routify';
	export let slug;

	$: languagesFolder = $components.find(
		({ meta }) => meta.name === 'languageEntries',
	);
	$: Language = languagesFolder.children.find(
		(node) => node.path.split('/').pop() === slug,
	);
</script>

<!-- routify:options index=300 -->
<div class="container">
	{#if Language}
		{#await Language.component then page}
			<svelte:component this={page} />
		{/await}
	{/if}
</div>

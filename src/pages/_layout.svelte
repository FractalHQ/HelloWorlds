<script>
	import {components, beforeUrlChange, layout, page, url} from '@roxi/routify'

	import Lang from '../components/Lang.svelte'

	// we want smooth scrolling when navigating (hash links) within the same page
	$beforeUrlChange(
		(event, newRoute) => (
			document.documentElement.style['scrollBehavior'] = newRoute === $page
				? 'smooth'
				: 'auto'
		)
	)
</script>

<main>
	<slot />
</main>

<nav>
	<div class="nav first">
		<div><Lang /></div>
	</div>
	<div class="nav last" />
</nav>

<style>
	main {
		padding-top: 50px;
	}
	nav {
		position: fixed;
		display: flex;
		justify-content: space-between;
		top: 0;
		left: 0;
		right: 0;
		height: 50px;
		padding: 8px;
	}
	nav div {
		display: flex;
		flex-basis: calc(100% / 3);
	}
	nav a {
		margin: 0 8px;
		font-size: 20px;
	}
</style>

<script>
	import { urlTransform } from './components/Lang.svelte';
	import { routes } from '../.routify/routes';
	import { Router } from '@roxi/routify';

	const config = {urlTransform};
</script>

<Router {routes} {config} />

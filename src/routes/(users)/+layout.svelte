<script lang="ts" module>
	import Footer from '$lib/components/externals/footer/footer.svelte';
	import Nav from '$lib/components/externals/nav/nav.svelte';
</script>

<script lang="ts">
	const { children } = $props();
</script>

<Nav />
{@render children()}
<Footer />

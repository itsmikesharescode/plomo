<script lang="ts">
	import Products from './(components)/(products)/products.svelte';
</script>

<div class="bg-slate-200">
	<div class="container mx-auto px-2 py-10">
		{#each Array(22)}
			<Products />
		{/each}
	</div>
</div>

<script lang="ts" module>
	import Pagination from './(components)/(pagination)/pagination.svelte';
	import Items from './(components)/(items)/items.svelte';
	import Header from './(components)/(header)/header.svelte';
	import OrderSummary from './(components)/(order-summary)/order-summary.svelte';
</script>

<script lang="ts">
</script>

<main class="container mx-auto grid grid-cols-[2fr_1fr] gap-8 p-2">
	<div class="">
		<Header />
		<div class="bg-white">
			{#each Array(20), index}
				<Items onCheckedChange={() => console.log(index)} />
			{/each}
		</div>
		<Pagination />
	</div>

	<div class="sticky top-16 h-fit">
		<OrderSummary />
	</div>
</main>

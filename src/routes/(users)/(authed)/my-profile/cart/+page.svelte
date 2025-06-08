<script lang="ts" module>
	import Pagination from './(components)/(pagination)/pagination.svelte';
	import Item from './(components)/(item)/item.svelte';
	import Header from './(components)/(header)/header.svelte';
	import OrderSummary from './(components)/(order-summary)/order-summary.svelte';
</script>

<script lang="ts">
</script>

<main class="container mx-auto grid gap-8 p-2 md:grid-cols-[2fr_1fr]">
	<div class="flex flex-col gap-4">
		<Header />
		<div class="flex flex-col gap-4 bg-white">
			{#each Array(20), index}
				<Item onCheckedChange={() => console.log(index)} />
			{/each}
		</div>
		<Pagination />
	</div>

	<div class="sticky top-16 h-fit">
		<OrderSummary />
	</div>
</main>

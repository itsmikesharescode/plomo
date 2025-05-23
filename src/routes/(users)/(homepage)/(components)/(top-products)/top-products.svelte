<script lang="ts">
	import * as Carousel from '$lib/components/internals/carousel/index';
	import type { CarouselAPI } from '$lib/components/internals/carousel/context';
	import ChevronLeft from '@tabler/icons-svelte/icons/chevron-left';
	import ChevronRight from '@tabler/icons-svelte/icons/chevron-right';
	import ProductCard from '$lib/components/externals/product-card/product-card.svelte';

	let api = $state<CarouselAPI>();

	const count = $derived(api ? api.scrollSnapList().length : 0);
	let current = $state(0);

	let canScrollPrev = $state(false);
	let canScrollNext = $state(false);

	$effect(() => {
		if (api) {
			current = api.selectedScrollSnap() + 1;
			canScrollPrev = api.canScrollPrev();
			canScrollNext = api.canScrollNext();
			api.on('select', () => {
				current = api!.selectedScrollSnap() + 1;
				canScrollPrev = api!.canScrollPrev();
				canScrollNext = api!.canScrollNext();
			});
		}
	});
</script>

<div class="relative container mx-auto flex flex-col gap-4 px-2 py-10">
	<span class="text-5xl font-bold">Top Products</span>

	<div class="grid gap-2 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-5">
		{#each Array(5)}
			<ProductCard />
		{/each}
	</div>
</div>

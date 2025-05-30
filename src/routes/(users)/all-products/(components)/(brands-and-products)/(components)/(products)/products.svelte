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
	<span class="text-5xl font-bold">Brand Name</span>
	<Carousel.Root setApi={(emblaApi) => (api = emblaApi)} class="w-full">
		<Carousel.Content class="p-2">
			{#each Array(10)}
				<Carousel.Item class="grid gap-2 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-5">
					{#each Array(5)}
						<ProductCard />
					{/each}
				</Carousel.Item>
			{/each}
		</Carousel.Content>
	</Carousel.Root>

	<div class="sticky bottom-4 flex items-center justify-between">
		<span class="text-muted-foreground py-2 text-center text-sm">
			Slide {current} of {count}
		</span>

		<div class="flex items-center justify-center gap-2">
			<button
				disabled={!canScrollPrev}
				onclick={() => {
					api?.scrollPrev();
				}}
				class={[
					'flex size-10 items-center justify-center rounded-full border',
					canScrollPrev ? 'bg-white transition-all hover:ring-2 active:scale-95' : 'bg-secondary'
				]}
			>
				<ChevronLeft class="text-muted-foreground size-4" />
			</button>
			<button
				disabled={!canScrollNext}
				onclick={() => {
					api?.scrollNext();
				}}
				class={[
					'flex size-10 items-center justify-center rounded-full border',
					canScrollNext ? 'bg-white transition-all hover:ring-2 active:scale-95' : 'bg-secondary'
				]}
			>
				<ChevronRight class="text-muted-black size-4" />
			</button>
		</div>
	</div>
</div>

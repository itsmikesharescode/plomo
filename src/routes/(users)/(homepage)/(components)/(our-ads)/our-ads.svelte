<script lang="ts">
	import * as Card from '$lib/components/internals/card/index.js';
	import * as Carousel from '$lib/components/internals/carousel/index.js';
</script>

<Carousel.Root opts={{ loop: true }} class="container mx-auto px-2 py-10">
	<Carousel.Content class="-ml-1">
		{#each Array(5) as _, i (i)}
			<Carousel.Item class="pl-1 md:basis-1/2 lg:basis-1/3">
				<div class="p-1">
					<Card.Root>
						<Card.Content class="flex aspect-square items-center justify-center p-6">
							<span class="text-2xl font-semibold">{i + 1}</span>
						</Card.Content>
					</Card.Root>
				</div>
			</Carousel.Item>
		{/each}
	</Carousel.Content>
</Carousel.Root>

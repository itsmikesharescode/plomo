<script lang="ts">
	import Button from '$lib/components/internals/button/button.svelte';
	import * as Card from '$lib/components/internals/card/index';
	import { goto } from '$app/navigation';
</script>

<Card.Root class="p-2">
	<Card.Content class="flex h-[300px] w-full flex-col gap-4 p-0">
		<a
			href="/all-products/brand-name/product-name"
			aria-label="photo"
			class="bg-secondary h-[200px] w-full rounded-lg transition-all duration-300 hover:scale-105 active:scale-95"
		>
		</a>

		<div class="flex flex-col gap-2">
			<span class="text-sm font-medium">Classic Leather Jacket</span>
			<span class="text-sm font-medium">₱ 500</span>
			<Button>Add to Cart</Button>
		</div>
	</Card.Content>
</Card.Root>

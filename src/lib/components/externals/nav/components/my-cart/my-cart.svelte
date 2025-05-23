<script lang="ts">
	import Button from '$lib/components/internals/button/button.svelte';
	import ShoppingCartCheck from '@tabler/icons-svelte/icons/shopping-cart-check';
</script>

<Button href="/cart" variant="outline">
	<ShoppingCartCheck class="text-muted-foreground size-5" />
	<span class="text-muted-foreground text-xs">My Cart</span>
</Button>

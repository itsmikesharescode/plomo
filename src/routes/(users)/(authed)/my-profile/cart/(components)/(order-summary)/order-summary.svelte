<script lang="ts">
	import IconTruck from '@tabler/icons-svelte/icons/truck';
	import IconMapPinFilled from '@tabler/icons-svelte/icons/map-pin-filled';
	import IconTicket from '@tabler/icons-svelte/icons/ticket';
	import { Button } from '$lib/components/internals/button/index.js';

	import { Input } from '$lib/components/internals/input/index.js';
</script>

<div class="border-muted-foreground h-fit rounded-lg border bg-white">
	<div class="border-muted-foreground flex flex-col gap-1 border-b">
		<span class="px-4 pt-4 text-sm font-medium"> Order Summary </span>

		<div class=" flex flex-col gap-1 p-4">
			{#each Array(3)}
				<div class="grid grid-cols-[1fr_auto]">
					<span class="text-muted-foreground line-clamp-1 text-xs">x2 Acne Shirt</span>
					<span class="line-clamp-1 text-xs font-medium">₱ 124,000</span>
				</div>
			{/each}
		</div>
	</div>

	<div class="border-muted-foreground flex flex-col gap-1 border-b">
		<div class="grid grid-cols-[1fr_auto]">
			<span class="text-muted-foreground px-4 pt-4 text-sm font-medium"> Delivery today with </span>
			<span class="px-4 pt-4 text-sm font-medium"> ₱ 124,000 </span>
		</div>

		<div class=" flex flex-col gap-1 p-4">
			<div class="grid grid-cols-[auto_1fr] items-center gap-2">
				<IconTruck class="text-muted-foreground size-4" />
				<span class="text-xs">Bullsht Express</span>
			</div>

			<div class="grid grid-cols-[auto_1fr] items-center gap-2">
				<IconMapPinFilled class="text-muted-foreground size-4" />
				<div class="flex items-center gap-1">
					<span class="text-muted-foreground text-xs">Deliver to</span>
					<span class="text-xs">Jakarta, Indonesia</span>
				</div>
			</div>
		</div>
	</div>

	<div class="border-muted-foreground flex flex-col gap-1 border-b p-4">
		<div class="grid grid-cols-[1fr_auto]">
			<span class="text-muted-foreground text-sm font-medium"> Amount </span>
			<span class="text-sm font-medium"> ₱ 124,000 </span>
		</div>

		<div class="grid grid-cols-[1fr_auto]">
			<span class="text-muted-foreground text-sm font-medium"> Tax </span>
			<span class="text-sm font-medium"> ₱ 5,000 </span>
		</div>
	</div>

	<div class="border-muted-foreground flex flex-col gap-1 border-b p-4">
		<div class="grid grid-cols-[1fr_auto] items-center">
			<span class="text-sm font-medium"> Order Total </span>
			<span class="text-xl font-medium"> ₱ 124,000 </span>
		</div>
	</div>

	<div class="flex flex-col gap-2 p-4">
		<div class="relative flex items-center">
			<IconTicket class="absolute left-5 size-4" />
			<Input placeholder="Add coupon code here" class="pl-14" />
		</div>
		<Button>Checkout</Button>
	</div>
</div>

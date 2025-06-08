<script lang="ts">
	import IconTruck from '@tabler/icons-svelte/icons/truck';
	import IconMapPinFilled from '@tabler/icons-svelte/icons/map-pin-filled';
	import IconTicket from '@tabler/icons-svelte/icons/ticket';
	import CreditCardPay from '@tabler/icons-svelte/icons/credit-card-pay';
	import { Button } from '$lib/components/internals/button/index';
	import * as Dialog from '$lib/components/internals/dialog/index';
	import { cn } from '$lib/utils';
	import type { ClassNameValue } from 'tailwind-merge';
	import { ScrollArea } from '$lib/components/internals/scroll-area/index';

	import { Input } from '$lib/components/internals/input/index.js';
</script>

{#snippet Summary({ class: classProp }: { class?: ClassNameValue })}
	<div class={cn('border-muted-foreground h-fit rounded-lg border bg-white', classProp)}>
		<div class="border-muted-foreground flex flex-col gap-1 border-b">
			<span class="px-4 pt-4 text-sm font-medium"> Order Summary </span>

			<ScrollArea>
				<div class="flex max-h-[40dvh] flex-col gap-1 p-4">
					{#each Array(20)}
						<div class="grid grid-cols-[1fr_auto]">
							<span class="text-muted-foreground line-clamp-1 text-xs">x2 Acne Shirt</span>
							<span class="line-clamp-1 text-xs font-medium">₱ 124,000</span>
						</div>
					{/each}
				</div>
			</ScrollArea>
		</div>

		<div class="border-muted-foreground flex flex-col gap-1 border-b">
			<div class="grid grid-cols-[1fr_auto]">
				<span class="text-muted-foreground px-4 pt-4 text-sm font-medium">
					Delivery today with
				</span>
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
{/snippet}

<Dialog.Root>
	<Dialog.Trigger
		class="bg-secondary border-primary fixed right-10 bottom-10 flex size-12 items-center justify-center rounded-full border-2 md:hidden"
	>
		<CreditCardPay class="size-5" />
	</Dialog.Trigger>

	<Dialog.Content class="p-0">
		<ScrollArea>
			{@render Summary({ class: 'w-full max-h-[100dvh]' })}
		</ScrollArea>
	</Dialog.Content>

	{@render Summary({ class: 'hidden md:block' })}
</Dialog.Root>

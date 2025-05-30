<script lang="ts">
	import * as AlertDialog from '$lib/components/internals/alert-dialog/index';
	import Search from '@tabler/icons-svelte/icons/search';
	import { buttonVariants } from '$lib/components/internals/button';
	import { Input } from '$lib/components/internals/input/index';
	import InputSearch from '@tabler/icons-svelte/icons/input-search';
	import X from '@tabler/icons-svelte/icons/x';
	import { ScrollArea } from '$lib/components/internals/scroll-area/index';
	import { Button } from '$lib/components/internals/button/index';
	let open = $state(false);
</script>

<AlertDialog.Root bind:open>
	<AlertDialog.Trigger
		class={buttonVariants({
			variant: 'outline',
			class: 'grid grid-cols-[auto_1fr] items-center gap-2'
		})}
	>
		<Search class="text-muted-foreground size-5" />
		<span class="text-muted-foreground text-xs">Search products</span>
	</AlertDialog.Trigger>
	<AlertDialog.Content class="">
		<div class="flex items-center gap-2">
			<InputSearch class="text-muted-foreground size-10" />
			<span class="text-muted-foreground text-xl">Find what you're looking for</span>
		</div>
		<Input placeholder="Search products" />

		<!--Search content-->
		<ScrollArea class="p-2">
			<div class="flex max-h-[55dvh] flex-col gap-2">
				{#each Array(20)}
					<div class="grid grid-cols-[auto_1fr] gap-2">
						<div class="bg-secondary size-20 rounded-lg"></div>
						<div class="bg-secondary/50 rounded-lg p-2">
							<div class="flex flex-col">
								<span class="text-muted-foreground">asdasdasdasd</span>
								<span class="text-muted-foreground text-xs">asdasdasdasd</span>
							</div>
							<span class="text-foreground font-semibold">₱ 500</span>
						</div>
					</div>
				{/each}
			</div>
		</ScrollArea>

		<span class="text-muted-foreground text-xs">Search Result: <b>20</b></span>

		<Button onclick={() => (open = false)} variant="ghost" class="ml-auto w-fit">
			<X class="text-muted-foreground size-4" />
			<span class="text-muted-foreground">Close</span>
		</Button>
	</AlertDialog.Content>
</AlertDialog.Root>

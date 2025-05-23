<script lang="ts">
	import * as Sheet from '$lib/components/internals/sheet/index';
	import Category from '@tabler/icons-svelte/icons/category';
	import { links } from '../../nav.svelte';
	import Button from '$lib/components/internals/button/button.svelte';
	import * as Accordion from '$lib/components/internals/accordion/index';
	import Profile from '$lib/components/externals/profile/profile.svelte';
	import { innerWidth } from 'svelte/reactivity/window';
	import SiteSearch from '../site-search/site-search.svelte';
	import MyCart from '../my-cart/my-cart.svelte';

	let open = $derived.by(() => {
		const isMobile = innerWidth.current && innerWidth.current < 768;

		if (isMobile) {
			return false;
		} else {
			return false;
		}
	});
</script>

<div class="flex w-full items-center justify-between md:hidden">
	<Sheet.Root bind:open>
		<Sheet.Trigger class="p-2">
			<Category class="text-muted-foreground size-6" />
		</Sheet.Trigger>
		<Sheet.Content side="left" class="bg-secondary flex flex-col justify-between">
			<div class="mt-20 flex flex-col px-2">
				{#each links as link}
					{#if link.childLinks}
						<Accordion.Root type="single" class="">
							<Accordion.Item value="item-1">
								<Accordion.Trigger class="px-4">{link.label}</Accordion.Trigger>
								<Accordion.Content class="p-2">
									{#each link.childLinks as childLink}
										<Button href={childLink.href} variant="link" class="w-full justify-start">
											{childLink.label}
										</Button>
									{/each}
								</Accordion.Content>
							</Accordion.Item>
						</Accordion.Root>
					{:else}
						<Button href={link.href} variant="link" class="mt-2 w-full justify-start">
							{link.label}
						</Button>
					{/if}
				{/each}
			</div>

			<div class="p-2">
				<Profile />
			</div>
		</Sheet.Content>
	</Sheet.Root>

	<div class="flex items-center gap-2">
		<div class="">
			<SiteSearch />
		</div>

		<div class="">
			<MyCart />
		</div>
	</div>
</div>

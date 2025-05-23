<script lang="ts">
	import { links } from '../../nav.svelte';
	import { NavigationMenu } from 'bits-ui';
	import CaretDown from '@tabler/icons-svelte/icons/caret-down';
	import SiteSearch from '../site-search/site-search.svelte';
	import MyCart from '../my-cart/my-cart.svelte';
	import Profile from '$lib/components/externals/profile/profile.svelte';
</script>

<NavigationMenu.Root class="relative z-10 hidden w-full items-center md:flex">
	<NavigationMenu.List class="group flex list-none items-center justify-center p-1">
		{#each links as link}
			{#if link.childLinks}
				<NavigationMenu.Item>
					<NavigationMenu.Trigger
						class="hover:text-accent-foreground focus:bg-muted focus:text-accent-foreground data-[state=open]:shadow-mini dark:hover:bg-muted dark:data-[state=open]:bg-muted group inline-flex h-8 w-max items-center justify-center rounded-[7px] bg-transparent px-4 py-2 text-sm font-medium transition-colors hover:bg-white focus:outline-hidden disabled:pointer-events-none disabled:opacity-50 data-[state=open]:bg-white"
					>
						{link.label}
						<CaretDown
							class="relative top-[1px] ml-1 size-3 transition-transform duration-200 group-data-[state=open]:rotate-180"
							aria-hidden="true"
						/>
					</NavigationMenu.Trigger>
					<NavigationMenu.Content
						class="data-[motion=from-end]:animate-enter-from-right data-[motion=from-start]:animate-enter-from-left data-[motion=to-end]:animate-exit-to-right data-[motion=to-start]:animate-exit-to-left absolute top-0 left-0 w-full sm:w-auto"
					>
						<ul class="grid gap-3 p-3 sm:w-[400px] sm:p-6 md:w-[500px] md:grid-cols-2 lg:w-[600px]">
							{#each link.childLinks as childLink}
								<NavigationMenu.Link
									class="hover:bg-muted hover:text-accent-foreground focus:bg-muted focus:text-accent-foreground grid grid-cols-[auto_1fr] items-center gap-5 space-y-1 rounded-md p-3 leading-none no-underline outline-hidden transition-colors select-none"
									href={childLink.href}
								>
									<childLink.Icon class="size-14" />
									<div class="flex h-full flex-col gap-2">
										<div class="text-sm leading-none font-medium">{childLink.label}</div>
										<p class="text-muted-foreground line-clamp-4 text-xs leading-snug">
											{childLink.description}
										</p>
									</div>
								</NavigationMenu.Link>
							{/each}
						</ul>
					</NavigationMenu.Content>
				</NavigationMenu.Item>
			{:else}
				<NavigationMenu.Item>
					<NavigationMenu.Link
						class="hover:text-accent-foreground focus:bg-muted focus:text-accent-foreground data-[state=open]:shadow-mini dark:hover:bg-muted dark:data-[state=open]:bg-muted group inline-flex h-8 w-max items-center justify-center rounded-[7px] bg-transparent px-4 py-2 text-sm font-medium transition-colors hover:bg-white focus:outline-hidden disabled:pointer-events-none disabled:opacity-50 data-[state=open]:bg-white"
						href={link.href}
					>
						<span class="hidden sm:inline"> {link.label} </span>
						<span class="inline sm:hidden"> {link.label} </span>
					</NavigationMenu.Link>
				</NavigationMenu.Item>
			{/if}
		{/each}

		<NavigationMenu.Indicator
			class="data-[state=hidden]:animate-fade-out data-[state=visible]:animate-fade-in top-full z-10 flex h-2.5 items-end justify-center overflow-hidden opacity-100 transition-[all,transform_250ms_ease] duration-200 data-[state=hidden]:opacity-0"
		>
			<div class="bg-border relative top-[70%] size-2.5 rotate-[45deg] rounded-tl-[2px]"></div>
		</NavigationMenu.Indicator>
	</NavigationMenu.List>
	<div class="absolute top-full left-0 flex w-full justify-start perspective-[2000px]">
		<NavigationMenu.Viewport
			class="text-popover-foreground bg-background data-[state=closed]:animate-scale-out data-[state=open]:animate-scale-in relative mt-2.5 h-[var(--bits-navigation-menu-viewport-height)] w-full origin-[top_center] overflow-hidden rounded-md border shadow-lg transition-[width,_height] duration-200 sm:w-[var(--bits-navigation-menu-viewport-width)] "
		/>
	</div>

	<div class="ml-auto flex items-center gap-2">
		<SiteSearch />
		<MyCart />
		<Profile />
	</div>
</NavigationMenu.Root>

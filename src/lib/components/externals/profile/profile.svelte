<script lang="ts">
	import DotsVerticalIcon from '@tabler/icons-svelte/icons/dots-vertical';
	import LogoutIcon from '@tabler/icons-svelte/icons/logout';
	import UserCircle from '@tabler/icons-svelte/icons/user-circle';
	import MapPins from '@tabler/icons-svelte/icons/map-pins';
	import TruckDelivery from '@tabler/icons-svelte/icons/truck-delivery';
	import * as Avatar from '$lib/components/internals/avatar/index.js';
	import * as DropdownMenu from '$lib/components/internals/dropdown-menu/index.js';
</script>

<DropdownMenu.Root>
	<DropdownMenu.Trigger class="flex w-full items-center gap-2 rounded-lg bg-white px-2 py-1">
		<Avatar.Root class="size-8 rounded-lg ">
			<Avatar.Image src="https://github.com/shadcn.png" alt="shadcn" />
			<Avatar.Fallback class="rounded-lg">CN</Avatar.Fallback>
		</Avatar.Root>
		<div class="grid flex-1 text-left text-sm leading-tight">
			<span class="truncate font-medium">asdasdasd</span>
			<span class="text-muted-foreground truncate text-xs"> asdasdasd </span>
		</div>
		<DotsVerticalIcon class="ml-auto size-4" />
	</DropdownMenu.Trigger>
	<DropdownMenu.Content
		class="w-(--bits-dropdown-menu-anchor-width) min-w-56 rounded-lg"
		side="bottom"
		align="end"
		sideOffset={4}
	>
		<DropdownMenu.Label class="p-0 font-normal">
			<div class="flex items-center gap-2 px-1 py-1.5 text-left text-sm">
				<Avatar.Root class="size-8 rounded-lg">
					<Avatar.Image src="https://github.com/shadcn.png" alt="shadcn" />
					<Avatar.Fallback class="rounded-lg">CN</Avatar.Fallback>
				</Avatar.Root>
				<div class="grid flex-1 text-left text-sm leading-tight">
					<span class="truncate font-medium">asdasdasd</span>
					<span class="text-muted-foreground truncate text-xs"> asdasdasd </span>
				</div>
			</div>
		</DropdownMenu.Label>
		<DropdownMenu.Separator />
		<DropdownMenu.Group>
			<a href="/addresses">
				<DropdownMenu.Item>
					<MapPins class="size-4" />
					Addresses
				</DropdownMenu.Item>
			</a>
			<DropdownMenu.Item>
				<TruckDelivery class="size-4" />
				Orders
			</DropdownMenu.Item>
		</DropdownMenu.Group>

		<DropdownMenu.Separator />
		<DropdownMenu.Item>
			<LogoutIcon />
			Log out
		</DropdownMenu.Item>
	</DropdownMenu.Content>
</DropdownMenu.Root>

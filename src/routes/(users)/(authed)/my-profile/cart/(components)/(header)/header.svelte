<script lang="ts">
	import * as DropdownMenu from '$lib/components/internals/dropdown-menu/index';
	import IconChevronDown from '@tabler/icons-svelte/icons/chevron-down';
</script>

<div class="bg-secondary sticky top-16 flex items-center justify-end gap-4 border px-4 py-2">
	<DropdownMenu.Root>
		<DropdownMenu.Trigger class="flex items-center">
			All Cart
			<IconChevronDown class="size-4" />
		</DropdownMenu.Trigger>
		<DropdownMenu.Content>
			<DropdownMenu.Group>
				<DropdownMenu.Label>Filter by cart idk</DropdownMenu.Label>
				<DropdownMenu.Separator />
				<DropdownMenu.Item>Filter 1</DropdownMenu.Item>
				<DropdownMenu.Item>Filter 2</DropdownMenu.Item>
				<DropdownMenu.Item>Filter 3</DropdownMenu.Item>
				<DropdownMenu.Item>Filter 4</DropdownMenu.Item>
			</DropdownMenu.Group>
		</DropdownMenu.Content>
	</DropdownMenu.Root>

	<DropdownMenu.Root>
		<DropdownMenu.Trigger class="flex items-center">
			Filter
			<IconChevronDown class="size-4" />
		</DropdownMenu.Trigger>
		<DropdownMenu.Content>
			<DropdownMenu.Group>
				<DropdownMenu.Label>Filter by idk</DropdownMenu.Label>
				<DropdownMenu.Separator />
				<DropdownMenu.Item>Filter 1</DropdownMenu.Item>
				<DropdownMenu.Item>Filter 2</DropdownMenu.Item>
				<DropdownMenu.Item>Filter 3</DropdownMenu.Item>
				<DropdownMenu.Item>Filter 4</DropdownMenu.Item>
			</DropdownMenu.Group>
		</DropdownMenu.Content>
	</DropdownMenu.Root>
</div>

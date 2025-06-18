<script lang="ts">
	import * as DropdownMenu from '$lib/components/internals/dropdown-menu/index';
	import IconChevronDown from '@tabler/icons-svelte/icons/chevron-down';
	import Search from '@tabler/icons-svelte/icons/search';
	import Input from '$lib/components/internals/input/input.svelte';
	import Checkbox from '$lib/components/internals/checkbox/checkbox.svelte';
	import { Label } from '$lib/components/internals/label/index';
</script>

<div class="bg-secondary sticky top-16 flex items-center justify-between gap-4 border px-4 py-2">
	<div class="flex items-center gap-3">
		<Checkbox id="select-all" class="bg-white" />
		<Label for="select-all" class="truncate">Select All</Label>
	</div>
	<div class="relative flex items-center gap-2">
		<Search class="absolute left-2 size-4" />
		<Input placeholder="Search" class="border-primary bg-transparent pl-8" />
	</div>
</div>

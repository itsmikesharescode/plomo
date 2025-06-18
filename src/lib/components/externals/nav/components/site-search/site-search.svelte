<script lang="ts">
	import Search from '@tabler/icons-svelte/icons/search';
	import Input from '$lib/components/internals/input/input.svelte';
	import { Debounced } from 'runed';
	import { goto } from '$app/navigation';

	let search = $state('');
	const debounced = new Debounced(() => search, 500);

	function handleKey(e: KeyboardEvent) {
		if (e.key === 'Enter') {
			goto(`/search?q=${encodeURIComponent(search)}`);
		}
	}

	function handleSubmit(e: Event) {
		e.preventDefault();
		goto(`/search?q=${encodeURIComponent(search)}`);
	}
</script>

<div class="relative flex w-full items-center gap-2">
	<form onsubmit={handleSubmit} class="contents">
		<Input
			placeholder="Search products"
			class="pl-8 text-sm"
			bind:value={search}
			onkeydown={handleKey}
		/>
		<Search class="absolute top-1/2 left-2 size-4 -translate-y-1/2" />
	</form>
</div>

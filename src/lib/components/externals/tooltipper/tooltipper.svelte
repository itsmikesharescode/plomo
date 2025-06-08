<script lang="ts">
	import * as Tooltip from '$lib/components/internals/tooltip/index';
	import type { Snippet } from 'svelte';

	interface Props {
		content: Snippet;
		description: string;
	}

	const { content, description }: Props = $props();
</script>

<Tooltip.Provider>
	<Tooltip.Root>
		<Tooltip.Trigger>
			{@render content()}
		</Tooltip.Trigger>
		<Tooltip.Content>
			<p>{description}</p>
		</Tooltip.Content>
	</Tooltip.Root>
</Tooltip.Provider>

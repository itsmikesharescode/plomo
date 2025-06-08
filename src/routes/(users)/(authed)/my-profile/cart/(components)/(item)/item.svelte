<script lang="ts">
	import { Badge } from '$lib/components/internals/badge/index';
	import { Button } from '$lib/components/internals/button/index';
	import { Checkbox } from '$lib/components/internals/checkbox/index';
	import TrashX from '@tabler/icons-svelte/icons/trash-x';
	import ToolTipper from '$lib/components/externals/tooltipper/tooltipper.svelte';

	interface Props {
		onCheckedChange?: (checked: boolean) => void;
	}

	const { onCheckedChange }: Props = $props();
</script>

<div class="bg-accent grid grid-cols-[auto_1fr] items-start gap-4 rounded-lg p-4">
	<ToolTipper description="Click to select this item.">
		{#snippet content()}
			<Checkbox {onCheckedChange} class="bg-white" />
		{/snippet}
	</ToolTipper>

	<div class="flex flex-col">
		<span class="text-muted-foreground text-2xl font-semibold">Acne Shirt</span>
		<span class="text-muted-foreground text-sm">Sample Category</span>

		<div class="grid items-center gap-4 md:grid-cols-[210px_1fr]">
			<div class="bg-secondary mt-4 h-[200px] w-full rounded-lg"></div>

			<div class="grid h-full gap-4 p-4">
				<div class="flex flex-col gap-4">
					<span class="line-clamp-3">
						Lorem ipsum, dolor sit amet consectetur adipisicing elit. Odit sequi, deserunt cum
						accusantium earum omnis itaque corrupti voluptatum nobis, voluptatem facere rem quasi.
						Ullam nulla quaerat assumenda molestiae, pariatur debitis repellat placeat officia
						nostrum dicta, provident tempore at maxime! Maxime deserunt facere quas magni eius
						repellat nulla quisquam expedita architecto? Consectetur voluptatem a perspiciatis
						ratione iste ad doloribus saepe nam eaque animi in, praesentium id, earum nihil. Ex sit
						libero blanditiis explicabo amet praesentium incidunt vitae facilis voluptates natus
						consectetur accusamus iusto rerum quia, exercitationem magnam eveniet sunt voluptatem
						itaque laborum earum sed in eaque. Iste dicta ipsum harum. Facilis odio ipsa eos. Ad
						unde ab nam placeat animi, enim nostrum, porro eum, quo quas iusto culpa libero ipsam?
						Atque impedit fugiat voluptates nisi qui ut, molestiae, soluta distinctio velit amet
						culpa! Autem nihil laboriosam corrupti est architecto consequuntur laborum impedit eius
						incidunt amet, numquam cupiditate aliquid quasi? Iure consectetur eos, voluptatum atque
						quibusdam nobis nesciunt hic officiis. Accusamus modi est repudiandae debitis minus
						nihil quasi ad impedit consequuntur error, dicta illo numquam veniam odio quia sint ea,
						aliquam earum molestiae, voluptatum expedita? Accusamus animi suscipit mollitia deserunt
						incidunt minima! Excepturi, optio eius illum temporibus inventore qui eum consequuntur
						laborum?
					</span>

					<Badge>Size: 200ml</Badge>
				</div>

				<div class="flex flex-col justify-between gap-4 md:flex-row md:items-end">
					<span>₱ 123,000</span>

					<div class="flex items-center gap-2">
						<ToolTipper description="Remove this item from your cart.">
							{#snippet content()}
								<Button variant="destructive" size="icon" class="rounded-full">
									<TrashX />
								</Button>
							{/snippet}
						</ToolTipper>

						<div class="grid grid-cols-[1fr_auto_1fr] items-center gap-2">
							<ToolTipper description="Decrease the quantity of this item.">
								{#snippet content()}
									<Button size="icon" class="rounded-full">-</Button>
								{/snippet}
							</ToolTipper>
							2
							<ToolTipper description="Increase the quantity of this item.">
								{#snippet content()}
									<Button size="icon" class="rounded-full">+</Button>
								{/snippet}
							</ToolTipper>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</div>

<script lang="ts">
	import { Badge } from '$lib/components/internals/badge/index';
	import { Button } from '$lib/components/internals/button/index';
	import { Checkbox } from '$lib/components/internals/checkbox/index';
	import TrashX from '@tabler/icons-svelte/icons/trash-x';

	interface Props {
		onCheckedChange?: (checked: boolean) => void;
	}

	const { onCheckedChange }: Props = $props();
</script>

<div class="grid grid-cols-[auto_1fr] items-start gap-4 p-4">
	<Checkbox {onCheckedChange} class="mt-2" />
	<div class="flex flex-col">
		<span class="text-muted-foreground text-2xl font-semibold">Acne Shirt</span>
		<span class="text-muted-foreground text-sm">Sample Category</span>

		<div class="grid grid-cols-[auto_1fr] items-center gap-4">
			<div class="bg-secondary mt-4 size-[200px] rounded-lg"></div>

			<div class="grid h-full p-4">
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

				<div class="flex items-end justify-between">
					<span>₱ 123,000</span>

					<div class="flex items-center gap-2">
						<Button variant="destructive" size="icon" class="rounded-full">
							<TrashX />
						</Button>
						<div class="grid grid-cols-[1fr_auto_1fr] items-center gap-2">
							<Button size="icon" class="rounded-full">-</Button>
							2
							<Button size="icon" class="rounded-full">+</Button>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</div>

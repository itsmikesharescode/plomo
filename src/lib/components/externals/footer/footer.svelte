<script lang="ts">
	import BrandGithub from '@tabler/icons-svelte/icons/brand-github';
	import BrandFacebook from '@tabler/icons-svelte/icons/brand-facebook';
</script>

<footer class="bg-secondary py-10">
	<div class="container mx-auto flex flex-col gap-4 p-2">
		<span class="text-sm font-medium">Made with ❤️ by <b>Mike</b> John</span>
		<div class="flex items-center gap-2">
			<a
				href="https://github.com/itsmikesharescode"
				target="_blank"
				class="rounded-full border bg-white p-2 transition-all duration-300"
			>
				<BrandGithub class="text-muted-foreground size-4" />
			</a>
			<a
				href="https://www.facebook.com/mike.eviota/"
				target="_blank"
				class="rounded-full border bg-white p-2 transition-all duration-300"
			>
				<BrandFacebook class="text-muted-foreground size-4" />
			</a>
		</div>
	</div>
</footer>

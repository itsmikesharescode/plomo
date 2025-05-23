<script lang="ts" module>
	import MobileScreen from './components/mobile-screen/mobile-screen.svelte';
	import DesktopScreen from './components/desktop-screen/desktop-screen.svelte';
	import Bulb from '@tabler/icons-svelte/icons/bulb';
	import QuestionMark from '@tabler/icons-svelte/icons/question-mark';

	export const links = [
		{
			label: 'Home',
			href: '/'
		},
		{
			label: 'All Products',
			href: '/all-products'
		},
		{
			label: 'Have a Request?',
			href: '#',
			childLinks: [
				{
					label: 'Request Product',
					href: '/request-product',
					description: 'Have an idea for a product? We can help you make it a reality.',
					Icon: Bulb
				},
				{
					label: 'Request Order',
					href: '/request-order',
					description: 'Want a custom product? We can help you get it.',
					Icon: QuestionMark
				}
			]
		}
	];
</script>

<script lang="ts">
</script>

<nav class="bg-secondary sticky top-0 z-40 border-b">
	<div class="container mx-auto flex items-center justify-between p-2">
		<MobileScreen />
		<DesktopScreen />
	</div>
</nav>

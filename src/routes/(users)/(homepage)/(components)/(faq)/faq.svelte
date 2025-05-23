<script lang="ts">
	import * as Accordion from '$lib/components/internals/accordion/index';

	const faqs = [
		{
			title: 'What is the refund policy?',
			answer:
				'We offer a 30-day money back guarantee. If you are not satisfied with our product, you can request a refund within 30 days of your purchase.'
		},
		{
			title: 'How do I create an account?',
			answer:
				'Click the "Sign Up" button in the top right corner and follow the registration process. You can use your email or social media accounts to register.'
		},
		{
			title: 'Is my data secure?',
			answer:
				'Yes, we use industry-standard encryption and security protocols to protect your data. All sensitive information is stored securely using AES-256 encryption.'
		},
		{
			title: 'What payment methods do you accept?',
			answer:
				'We accept all major credit cards (Visa, Mastercard, American Express), PayPal, and bank transfers.'
		},
		{
			title: 'How can I reset my password?',
			answer:
				'Go to the login page and click "Forgot Password". Enter your email address and follow the instructions sent to your inbox.'
		},
		{
			title: 'Do you offer team accounts?',
			answer:
				'Yes, we offer team plans with collaborative features. You can upgrade your account in the billing section and invite team members.'
		},
		{
			title: 'Can I cancel my subscription anytime?',
			answer:
				"Absolutely. You can cancel your subscription in the billing settings, and you'll continue to have access until the end of your billing period."
		},
		{
			title: 'How often are new features added?',
			answer:
				'We release updates every 2 weeks with new features, improvements, and bug fixes based on user feedback.'
		},
		{
			title: 'What browsers are supported?',
			answer:
				'Our platform works best with Chrome, Firefox, Safari, and Edge. We recommend using the latest browser versions for optimal performance.'
		},
		{
			title: 'How can I contact support?',
			answer:
				'Our support team is available 24/7 through the in-app chat or via email at support@example.com. Average response time is under 1 hour.'
		}
	];
</script>

<div class="py-20">
	<div class="container mx-auto flex flex-col gap-5 p-2">
		<div class="flex flex-col items-center gap-2">
			<span class="text-3xl font-semibold">Frequently Asked Questions</span>
			<span class="text-muted-foreground text-sm">
				Discover quick and comprehensive answers to common questions about our platform, services,
				and features.
			</span>
		</div>

		<Accordion.Root type="single">
			{#each faqs as faq, i}
				<Accordion.Item value={`item-${i + 1}`}>
					<Accordion.Trigger>{faq.title}</Accordion.Trigger>
					<Accordion.Content class="text-muted-foreground">{faq.answer}</Accordion.Content>
				</Accordion.Item>
			{/each}
		</Accordion.Root>
	</div>
</div>

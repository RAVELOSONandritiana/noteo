<div class="py-24">
	<div class="mx-auto max-w-7xl px-6 lg:px-8">
		<div class="grid grid-cols-1 gap-12 lg:grid-cols-4">
			<aside class="space-y-4 lg:col-span-1">
				<h3 class="mb-6 text-xs font-bold tracking-widest text-gray-900 uppercase dark:text-white">
					Documentation
				</h3>
				<nav class="space-y-1">
					{#each ['Authentication', 'Note Management', 'AI Endpoints', 'Webhooks', 'SDKs'] as item}
						<a
							href="#"
							class="block rounded-lg px-4 py-2 text-sm text-gray-600 hover:bg-gray-100 dark:text-gray-400 dark:hover:bg-gray-800"
							>{item}</a
						>
					{/each}
				</nav>
			</aside>
			<main class="prose max-w-none lg:col-span-3 dark:prose-invert">
				<h1>API Documentation</h1>
				<p>
					Welcome to the Noteo API. Our API allows you to programmatically access your notes,
					trigger AI enhancements, and integrate Noteo with your own educational tools.
				</p>
				<pre class="rounded-2xl bg-gray-900 p-6 text-blue-400"><code
						>curl -X GET "https://api.noteo.inc/v1/notes" \
  -H "Authorization: Bearer YOUR_TOKEN"</code
					></pre>
			</main>
		</div>
	</div>
</div>

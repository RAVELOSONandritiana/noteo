<div class="min-h-screen bg-white transition-colors duration-500 dark:bg-gray-950">
	<div class="mx-auto max-w-7xl px-6 py-24 sm:py-32 lg:px-8">
		<div class="grid grid-cols-1 gap-16 lg:grid-cols-12">
			<!-- Sidebar -->
			<aside class="lg:col-span-3">
				<nav class="sticky top-24 space-y-1">
					<p class="mb-6 px-4 text-[10px] font-black tracking-widest text-blue-600 uppercase">
						Introduction
					</p>
					{#each ['Getting Started', 'Authentication', 'Errors'] as item}
						<a
							href="#"
							class="block rounded-xl px-4 py-3 text-sm font-bold text-gray-400 transition-all hover:bg-blue-50 hover:text-blue-600 dark:hover:bg-blue-900/20"
							>{item}</a
						>
					{/each}
					<p class="mt-12 mb-6 px-4 text-[10px] font-black tracking-widest text-blue-600 uppercase">
						Endpoints
					</p>
					{#each ['Notes API', 'AI Context', 'Transcription', 'Diagrams'] as item}
						<a
							href="#"
							class="block rounded-xl px-4 py-3 text-sm font-bold text-gray-400 transition-all hover:bg-blue-50 hover:text-blue-600 dark:hover:bg-blue-900/20"
							>{item}</a
						>
					{/each}
				</nav>
			</aside>

			<!-- Main Content -->
			<main class="max-w-3xl lg:col-span-9">
				<h1 class="mb-8 text-4xl font-black text-gray-900 dark:text-white">API Documentation</h1>
				<p class="mb-12 text-xl text-gray-600 dark:text-gray-400">
					Build educational magic. The Noteo API gives you programatic access to our core extraction
					and synthesis engines.
				</p>

				<div class="space-y-16">
					<section>
						<h2 class="mb-6 text-2xl font-black text-gray-900 dark:text-white">Authentication</h2>
						<p class="mb-6 leading-relaxed text-gray-600 dark:text-gray-400">
							Most API requests require a Bearer token in the header. You can generate one in your
							developer settings.
						</p>
						<div class="group relative">
							<div
								class="absolute -inset-2 rounded-2xl bg-gradient-to-r from-blue-600 to-indigo-600 opacity-0 blur transition-opacity group-hover:opacity-10"
							></div>
							<div class="relative rounded-2xl border border-white/5 bg-gray-900 p-8 shadow-2xl">
								<div class="mb-4 flex items-center justify-between">
									<div class="flex gap-1.5">
										<div class="h-2.5 w-2.5 rounded-full bg-red-500/30"></div>
										<div class="h-2.5 w-2.5 rounded-full bg-yellow-500/30"></div>
										<div class="h-2.5 w-2.5 rounded-full bg-green-500/30"></div>
									</div>
									<span class="text-[10px] font-bold tracking-widest text-gray-500 uppercase"
										>cURL</span
									>
								</div>
								<pre class="overflow-x-auto"><code
										class="font-mono text-sm leading-relaxed text-blue-400"
										>curl -X GET "https://api.noteo.inc/v1/notes" \<br
										/>  -H "Authorization: Bearer YOUR_TOKEN"</code
									></pre>
							</div>
						</div>
					</section>

					<section>
						<h2 class="mb-6 text-2xl font-black text-gray-900 dark:text-white">Note Management</h2>
						<p class="leading-relaxed text-gray-600 dark:text-gray-400">
							Create, fetch, update, and delete notes. Notes are stored as semantic graphs
							internally to allow for high-speed AI retrieval.
						</p>
					</section>
				</div>
			</main>
		</div>
	</div>
</div>

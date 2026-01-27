<div class="py-24">
	<div class="mx-auto max-w-7xl px-6 lg:px-8">
		<div class="mb-16 text-center">
			<h1 class="text-4xl font-black text-gray-900 sm:text-5xl dark:text-white">Noteo Blog</h1>
			<p class="mt-4 font-medium text-gray-600 italic dark:text-gray-400">
				Latest updates from the team
			</p>
		</div>

		<div class="grid grid-cols-1 gap-10 md:grid-cols-2 lg:grid-cols-3">
			{#each [{ title: 'The Future of AI in Education', date: 'Jan 24, 2026', author: 'Dr. Elena Rossi' }, { title: '10 Tips for Better Note-taking', date: 'Jan 20, 2026', author: 'Sarah Miller' }, { title: 'Designing Noteo 2.0', date: 'Jan 15, 2026', author: 'James Chen' }] as post}
				<div
					class="group overflow-hidden rounded-3xl border border-gray-100 bg-white shadow-sm transition-all hover:shadow-xl dark:border-gray-800 dark:bg-gray-900"
				>
					<div class="h-48 bg-gray-100 dark:bg-gray-800"></div>
					<div class="p-8">
						<p class="mb-2 text-xs font-bold tracking-wide text-blue-600 uppercase">{post.date}</p>
						<h3
							class="mb-4 text-xl font-bold text-gray-900 transition-colors group-hover:text-blue-600 dark:text-white"
						>
							{post.title}
						</h3>
						<p class="text-sm text-gray-500 dark:text-gray-400">By {post.author}</p>
					</div>
				</div>
			{/each}
		</div>
	</div>
</div>

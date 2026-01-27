<div class="py-24">
	<div class="mx-auto max-w-7xl px-6 lg:px-8">
		<div class="mx-auto mb-20 max-w-2xl text-center">
			<h1 class="mb-6 text-4xl font-black text-gray-900 sm:text-5xl dark:text-white">
				How can we help?
			</h1>
			<div class="relative">
				<input
					type="text"
					placeholder="Search for articles..."
					class="w-full rounded-2xl border border-gray-200 bg-white px-6 py-4 shadow-lg outline-none focus:border-transparent focus:ring-2 focus:ring-blue-600 dark:border-gray-800 dark:bg-gray-900 dark:text-white"
				/>
			</div>
		</div>

		<div class="grid grid-cols-1 gap-8 md:grid-cols-3">
			{#each [{ t: 'Getting Started', d: 'New to Noteo? Start here.', i: '📖' }, { t: 'Account & Billing', d: 'Manage your subscription.', i: '💳' }, { t: 'AI & Tools', d: 'Learn how to use AI features.', i: '✨' }] as cat}
				<div
					class="rounded-3xl border border-gray-100 bg-white p-10 text-center transition-all hover:border-blue-200 dark:border-gray-800 dark:bg-gray-950"
				>
					<div class="mb-4 text-4xl">{cat.i}</div>
					<h3 class="mb-2 text-xl font-bold text-gray-900 dark:text-white">{cat.t}</h3>
					<p class="text-sm text-gray-500 dark:text-gray-400">{cat.d}</p>
				</div>
			{/each}
		</div>
	</div>
</div>

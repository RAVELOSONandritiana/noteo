<div class="py-24 sm:py-32">
	<div class="mx-auto max-w-7xl px-6 lg:px-8">
		<div class="mx-auto mb-24 max-w-3xl text-center">
			<h2 class="mb-6 text-xs font-bold tracking-widest text-blue-600 uppercase">Support</h2>
			<h1 class="mb-8 text-4xl font-black text-gray-900 sm:text-6xl dark:text-white">
				How can we <span
					class="bg-gradient-to-r from-blue-600 to-indigo-600 bg-clip-text text-transparent"
					>Help</span
				>?
			</h1>
			<div class="relative mx-auto max-w-xl rounded-[1.5rem] shadow-2xl">
				<input
					type="text"
					placeholder="Search for documentation, guides, and tips..."
					class="w-full rounded-[1.5rem] border border-gray-100 bg-white px-8 py-6 font-medium text-gray-900 transition-all outline-none focus:ring-4 focus:ring-blue-600/10 dark:border-gray-800 dark:bg-gray-900 dark:text-white"
				/>
				<div class="absolute top-1/2 right-6 -translate-y-1/2 text-gray-400">⌘K</div>
			</div>
		</div>

		<div class="grid grid-cols-1 gap-8 md:grid-cols-2 lg:grid-cols-4">
			{#each [{ t: 'Getting Started', d: 'Master the basics of Noteo in under 5 minutes.', i: '📖' }, { t: 'AI Customization', d: 'Tune the extraction engine to your subject.', i: '✨' }, { t: 'Collaborative Study', d: 'Work with groups and sync knowledge.', i: '🤝' }, { t: 'Account & Privacy', d: 'Manage your data and security settings.', i: '🛡️' }] as cat}
				<div
					class="group cursor-pointer rounded-[2.5rem] border border-gray-100 bg-white p-10 transition-all hover:border-blue-600 hover:bg-blue-600 hover:shadow-2xl hover:shadow-blue-500/30 dark:border-gray-800 dark:bg-gray-900"
				>
					<div class="mb-6 text-4xl grayscale transition-all group-hover:grayscale-0">{cat.i}</div>
					<h3
						class="mb-2 text-xl font-bold text-gray-900 transition-colors group-hover:text-white dark:text-white"
					>
						{cat.t}
					</h3>
					<p
						class="text-sm leading-relaxed text-gray-500 transition-colors group-hover:text-blue-50 dark:text-gray-400"
					>
						{cat.d}
					</p>
				</div>
			{/each}
		</div>

		<div
			class="mt-32 flex flex-col items-center rounded-[3.5rem] border border-gray-100 bg-gray-50 p-12 text-center dark:border-gray-800 dark:bg-gray-900/10"
		>
			<h3 class="mb-4 text-2xl font-black text-gray-900 dark:text-white">Still need assistance?</h3>
			<p class="mb-8 text-gray-500 dark:text-gray-400">
				Our community-run support desk is available 24/7 for critical inquiries.
			</p>
			<a
				href="/contact"
				class="rounded-2xl bg-gray-900 px-10 py-4 font-bold text-white transition-all hover:scale-105 active:scale-95 dark:bg-white dark:text-gray-900"
				>Contact Human Support</a
			>
		</div>
	</div>
</div>

<div class="py-24 sm:py-32">
	<div class="mx-auto max-w-7xl px-6 lg:px-8">
		<div class="mx-auto mb-16 max-w-2xl text-center">
			<h2 class="mb-4 text-xs font-bold tracking-widest text-blue-600 uppercase">Careers</h2>
			<h1 class="mb-6 text-4xl font-black text-balance text-gray-900 sm:text-5xl dark:text-white">
				Help us build the <span class="text-blue-600">future of learning</span>.
			</h1>
			<p class="mx-auto max-w-xl leading-relaxed text-gray-600 dark:text-gray-400">
				We're looking for passionate individuals to join our remote-first team and shape the next
				generation of AI educational tools.
			</p>
		</div>

		<div class="mx-auto max-w-3xl space-y-6">
			{#each [{ title: 'Senior NLP Engineer', team: 'AI Research', location: 'Remote (US/EU)' }, { title: 'Product Designer', team: 'Design', location: 'Remote (Global)' }, { title: 'Full Stack Developer', team: 'Engineering', location: 'Remote (Global)' }] as job}
				<div
					class="group flex items-center justify-between rounded-2xl border border-gray-100 bg-white p-8 shadow-sm transition-all hover:border-blue-200 dark:border-gray-800 dark:bg-gray-900 dark:hover:border-blue-900/50"
				>
					<div>
						<h3 class="mb-2 text-xl font-bold text-gray-900 dark:text-white">{job.title}</h3>
						<div class="flex gap-4 text-sm text-gray-500 dark:text-gray-400">
							<span>{job.team}</span>
							<span>•</span>
							<span>{job.location}</span>
						</div>
					</div>
					<button
						class="rounded-xl bg-gray-100 px-6 py-2 font-bold text-gray-900 transition-all group-hover:bg-blue-600 group-hover:text-white dark:bg-gray-800 dark:text-white"
						>Apply</button
					>
				</div>
			{/each}
		</div>
	</div>
</div>

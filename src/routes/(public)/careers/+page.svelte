<div class="relative py-24 sm:py-32">
	<div class="mx-auto max-w-7xl px-6 lg:px-8">
		<div class="mx-auto mb-24 max-w-2xl text-center">
			<h2 class="mb-6 text-xs font-bold tracking-widest text-blue-600 uppercase">Join Noteo</h2>
			<h1 class="mb-8 text-4xl font-black text-gray-900 sm:text-6xl dark:text-white">
				Work that <span
					class="bg-gradient-to-r from-blue-600 to-indigo-600 bg-clip-text text-transparent"
					>Matters</span
				>.
			</h1>
			<p class="text-lg text-gray-600 dark:text-gray-400">
				We're a distributed team of researchers and builders obsessed with one thing: solving the
				knowledge-retention crisis.
			</p>
		</div>

		<div class="mx-auto max-w-4xl space-y-8">
			{#each [{ title: 'Senior NLP Research Engineer', team: 'Intelligence', loc: 'Remote', salary: '$140k - $190k' }, { title: 'Product Designer (LMS/Edu)', team: 'Design', loc: 'Remote', salary: '$110k - $150k' }, { title: 'Full Stack Svelte Expert', team: 'Platform', loc: 'Remote', salary: '$120k - $170k' }, { title: 'Curriculum Specialist', team: 'Education', loc: 'Remote', salary: '$90k - $130k' }] as job}
				<div
					class="group relative rounded-3xl border border-gray-100 bg-white p-8 shadow-sm transition-all duration-300 hover:border-blue-200 hover:shadow-2xl dark:border-gray-800 dark:bg-gray-900 dark:hover:border-blue-900/50"
				>
					<div class="flex flex-col justify-between gap-6 md:flex-row md:items-center">
						<div>
							<div
								class="mb-4 inline-flex rounded-full bg-blue-50 px-3 py-1 text-[10px] font-bold tracking-widest text-blue-600 uppercase dark:bg-blue-900/30 dark:text-blue-400"
							>
								{job.team}
							</div>
							<h3 class="mb-2 text-2xl font-black text-gray-900 dark:text-white">{job.title}</h3>
							<div class="flex gap-6 text-sm text-gray-500 dark:text-gray-400">
								<span class="flex items-center gap-1">📍 {job.loc}</span>
								<span class="flex items-center gap-1">💰 {job.salary}</span>
							</div>
						</div>
						<button
							class="rounded-2xl bg-blue-600 px-8 py-4 text-center font-bold text-white transition-all hover:scale-[1.02] hover:bg-blue-700 active:scale-95"
						>
							Apply Now
						</button>
					</div>
				</div>
			{/each}
		</div>

		<!-- Culture Note -->
		<div
			class="mx-auto mt-32 max-w-5xl rounded-[3.5rem] border border-gray-100 bg-gray-50 p-12 text-center dark:border-gray-800 dark:bg-gray-900/30"
		>
			<h3 class="mb-6 text-3xl font-black text-gray-900 dark:text-white">Our Radical Values</h3>
			<div class="mt-12 grid grid-cols-1 gap-12 sm:grid-cols-3">
				<div>
					<div class="mb-4 text-3xl">🚀</div>
					<h4 class="mb-2 font-bold dark:text-white">Autonomy-First</h4>
					<p class="text-sm text-gray-500">We hire experts and trust them to lead.</p>
				</div>
				<div>
					<div class="mb-4 text-3xl">🧪</div>
					<h4 class="mb-2 font-bold dark:text-white">Research-Driven</h4>
					<p class="text-sm text-gray-500">Decisions are made based on data, not egos.</p>
				</div>
				<div>
					<div class="mb-4 text-3xl">🏳️‍🌈</div>
					<h4 class="mb-2 font-bold dark:text-white">True Inclusion</h4>
					<p class="text-sm text-gray-500">Diverse minds built the best AI.</p>
				</div>
			</div>
		</div>
	</div>
</div>

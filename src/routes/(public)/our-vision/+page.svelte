<div class="relative overflow-hidden py-24 sm:py-32">
	<div class="mx-auto max-w-7xl px-6 lg:px-8">
		<div class="grid grid-cols-1 items-center gap-24 lg:grid-cols-2">
			<div>
				<h2 class="mb-6 text-xs font-bold tracking-widest text-blue-600 uppercase">The Horizon</h2>
				<h1 class="mb-10 text-5xl leading-tight font-black text-gray-900 dark:text-white">
					A world where <br /><span class="text-blue-600">understanding</span> is the only limit.
				</h1>
				<div class="space-y-8 text-lg text-gray-600 dark:text-gray-400">
					<p>
						We believe that technology should be an invisible bridge, not a barrier. Noteo was
						founded to solve a singular problem: the massive cognitive leak that happens during
						lectures and technical research.
					</p>
					<div class="border-l-4 border-blue-600 bg-blue-50/50 p-8 italic dark:bg-blue-900/20">
						"We aren't building a tool to record words. We are building a system to capture
						comprehension."
					</div>
					<p>
						Our vision is to democratize high-level academic success, ensuring that every student,
						regardless of their background or learning speed, has an advisor sitting right next to
						them.
					</p>
				</div>
			</div>
			<div class="relative">
				<div
					class="absolute -inset-10 animate-pulse rounded-full bg-blue-500/10 blur-[120px] dark:bg-blue-600/10"
				></div>
				<div
					class="relative flex aspect-[4/5] items-center justify-center rounded-[4rem] border border-gray-200 bg-gray-100 p-12 shadow-inner dark:border-gray-700 dark:bg-gray-800"
				>
					<div class="text-center">
						<div class="mb-8 text-8xl">💡</div>
						<div class="mx-auto mb-8 h-1 w-24 rounded-full bg-blue-600"></div>
						<p class="text-2xl font-black text-gray-900 dark:text-gray-100">
							AI-Augmented Learning
						</p>
						<p class="mt-4 text-sm tracking-[0.2em] text-gray-400 uppercase">Strategy 2026-2030</p>
					</div>
				</div>
			</div>
		</div>

		<!-- Vision Pillars -->
		<div class="mt-48 grid grid-cols-1 gap-12 md:grid-cols-3">
			{#each [{ t: 'Cognitive Offloading', d: 'Removing the burden of transcription to focus purely on active synthesis.', i: '🧠' }, { t: 'Instant Context', d: 'Semantic retrieval of knowledge exactly when it is needed most.', i: '⚡' }, { t: 'Universal Access', d: 'Breaking language and technical barriers for every subject worldwide.', i: '🎙️' }] as pillar}
				<div
					class="relative rounded-[2.5rem] border border-gray-100 bg-white p-10 shadow-sm transition-all hover:shadow-2xl dark:border-gray-800 dark:bg-gray-900"
				>
					<div class="mb-6 text-4xl">{pillar.i}</div>
					<h3 class="mb-4 text-xl font-black text-gray-900 dark:text-white">{pillar.t}</h3>
					<p class="text-sm leading-relaxed text-gray-600 dark:text-gray-400">{pillar.d}</p>
				</div>
			{/each}
		</div>
	</div>
</div>

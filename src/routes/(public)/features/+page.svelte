<div class="relative isolate overflow-hidden py-24 sm:py-32">
	<!-- Background -->
	<div class="absolute inset-0 -z-10 bg-white transition-colors duration-500 dark:bg-gray-950">
		<div
			class="absolute top-0 left-1/2 h-[500px] w-full -translate-x-1/2 bg-gradient-to-b from-blue-50/50 to-transparent opacity-50 blur-3xl dark:from-blue-900/10"
		></div>
	</div>

	<div class="mx-auto max-w-7xl px-6 lg:px-8">
		<div class="mx-auto mb-20 max-w-2xl text-center">
			<h2 class="mb-4 text-xs font-bold tracking-widest text-blue-600 uppercase">The Platform</h2>
			<h1 class="mb-6 text-4xl font-black text-gray-900 sm:text-6xl dark:text-white">
				Unleash your <span
					class="bg-gradient-to-r from-blue-600 to-indigo-600 bg-clip-text text-transparent"
					>Full Potential</span
				>.
			</h1>
			<p class="text-lg text-gray-600 dark:text-gray-400">
				Noteo integrates seamlessly into your learning workflow, providing high-fidelity tools for a
				digital-first education.
			</p>
		</div>

		<div class="grid grid-cols-1 gap-8 md:grid-cols-2">
			{#each [{ t: 'Demand-based Completion', d: 'Focus on the essentials. Note down fragments and trigger the AI to fill in the gaps with academic-grade depth and context.', i: '🧠', c: 'blue' }, { t: 'Live Session Focus', d: 'A distraction-free interface optimized for real-time capture during fast-paced lectures and professional conferences.', i: '🧘', c: 'emerald' }, { t: 'Diagram Generation', d: 'Convert your text descriptions directly into Mermaid graphs or flowcharts with simple natural language commands.', i: '📊', c: 'purple' }, { t: 'Semantic Linking', d: 'Noteo builds a Knowledge Graph of your learning, showing how concepts from different classes connect automatically.', i: '🔗', c: 'cyan' }, { t: 'Real-time Transcription', d: 'Highest accuracy speech-to-text engine that handles technical jargon and multiple accents with ease.', i: '🎙️', c: 'indigo' }, { t: 'Collaborative Sync', d: 'Sync your notes across devices instantly and share them with your study groups for real-time peer review.', i: '☁️', c: 'sky' }] as feat}
				<div class="group relative p-1 transition-all hover:scale-[1.01]">
					<div
						class="absolute -inset-0.5 rounded-[2rem] bg-gradient-to-r from-blue-500 to-indigo-600 opacity-0 blur transition-opacity group-hover:opacity-20"
					></div>
					<div
						class="relative h-full rounded-[2rem] border border-gray-100 bg-white p-10 shadow-sm backdrop-blur-sm transition-all hover:shadow-2xl dark:border-gray-800 dark:bg-gray-900/80"
					>
						<div
							class="mb-8 flex h-14 w-14 items-center justify-center rounded-2xl bg-blue-50 text-3xl italic shadow-inner transition-transform group-hover:rotate-6 dark:bg-blue-900/30"
						>
							{feat.i}
						</div>
						<h3 class="mb-4 text-2xl font-black text-gray-900 dark:text-white">{feat.t}</h3>
						<p class="leading-relaxed text-gray-600 dark:text-gray-400">{feat.d}</p>
					</div>
				</div>
			{/each}
		</div>
	</div>
</div>

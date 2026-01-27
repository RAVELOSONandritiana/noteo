<div class="py-24">
	<div class="mx-auto max-w-7xl px-6 lg:px-8">
		<h2 class="mb-4 text-center text-xs font-bold tracking-widest text-blue-600 uppercase">
			Features
		</h2>
		<h1
			class="mb-16 text-center text-4xl font-black text-balance text-gray-900 sm:text-6xl dark:text-white"
		>
			Tools designed for <span class="text-blue-600">deep learning</span>.
		</h1>

		<div class="grid grid-cols-1 gap-12 md:grid-cols-2">
			{#each [{ t: 'Smart AI Context', d: 'Noteo understands the subject matter and provides contextually relevant definitions.', i: '🧠' }, { t: 'Real-time Transcription', d: 'Capture every word with our advanced speech-to-text engine.', i: '🎙️' }, { t: 'Diagram Generation', d: 'Instantly turn text descriptions into visual Mermaid diagrams.', i: '📊' }, { t: 'Cloud Synchronization', d: 'Access your notes from any device, anywhere in the world.', i: '☁️' }] as feat}
				<div
					class="rounded-3xl border border-gray-100 bg-gray-50 p-8 dark:border-gray-800 dark:bg-gray-900/50"
				>
					<div class="mb-6 text-4xl">{feat.i}</div>
					<h3 class="mb-4 text-2xl font-bold text-gray-900 dark:text-white">{feat.t}</h3>
					<p class="leading-relaxed text-gray-600 dark:text-gray-400">{feat.d}</p>
				</div>
			{/each}
		</div>
	</div>
</div>

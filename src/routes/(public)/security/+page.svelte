<div class="py-24 sm:py-32">
	<div class="mx-auto max-w-7xl px-6 lg:px-8">
		<div class="mb-24 max-w-2xl">
			<h2 class="mb-6 text-xs font-bold tracking-widest text-blue-600 uppercase">Security</h2>
			<h1 class="mb-8 text-5xl font-black text-gray-900 dark:text-white">
				Zero-Knowledge <br /><span class="text-blue-600">Integrity</span>.
			</h1>
			<p class="text-xl leading-relaxed text-gray-600 dark:text-gray-400">
				Your education is your intellectual property. We treat it with the highest standards of
				cryptographic security and data sovereignty.
			</p>
		</div>

		<div class="mb-32 grid grid-cols-1 gap-12 md:grid-cols-2">
			{#each [{ t: 'End-to-End Encryption', d: 'Optional e2ee for sensitive research notes. Only your device holds the keys.', i: '🔐' }, { t: 'GDPR & SOC 2', d: 'We adhere to the strictest global privacy regulations for educational data.', i: '⚖️' }, { t: 'Audit Logs', d: 'Complete transparency on every account interaction and data access request.', i: '📄' }, { t: 'Safe AI Training', d: 'Your personal notes are never used to train public LLMs. Ever.', i: '🚫' }] as sec}
				<div
					class="rounded-[3rem] border border-gray-100 bg-white p-10 shadow-xl dark:border-gray-800 dark:bg-gray-900"
				>
					<div class="mb-8 text-4xl">{sec.i}</div>
					<h3 class="mb-4 text-2xl font-black text-gray-900 dark:text-white">{sec.t}</h3>
					<p class="leading-relaxed text-gray-600 dark:text-gray-400">{sec.d}</p>
				</div>
			{/each}
		</div>

		<!-- Status indicator banner -->
		<div
			class="shadow-3xl flex flex-col items-center justify-between gap-12 rounded-[4rem] bg-blue-600 p-12 text-white shadow-blue-500/20 md:flex-row"
		>
			<div class="max-w-md">
				<div
					class="mb-6 inline-flex items-center gap-2 rounded-full bg-white/20 px-3 py-1 text-xs font-bold tracking-widest uppercase"
				>
					System Status
				</div>
				<h3 class="mb-4 text-3xl font-black">Noteo is secure and operational.</h3>
				<p class="text-blue-100 italic">No incidents reported in the last 180 days.</p>
			</div>
			<div class="flex gap-4">
				<button
					class="rounded-2xl bg-white px-10 py-4 font-black text-blue-600 shadow-xl transition-all hover:scale-105 active:scale-95"
					>Security Report</button
				>
			</div>
		</div>
	</div>
</div>

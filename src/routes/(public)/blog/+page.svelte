<div class="py-24 sm:py-32">
	<div class="mx-auto max-w-7xl px-6 lg:px-8">
		<div class="mb-24 max-w-3xl">
			<h2 class="mb-6 text-xs font-bold tracking-widest text-blue-600 uppercase">Noteo Journal</h2>
			<h1 class="mb-8 text-5xl font-black text-gray-900 dark:text-white">
				Ideas across the <span
					class="bg-gradient-to-r from-blue-600 to-indigo-600 bg-clip-text text-transparent"
					>Digital Classroom</span
				>.
			</h1>
			<p class="text-xl text-gray-600 dark:text-gray-400">
				Explorations in AI, cognitive science, and the evolving nature of education.
			</p>
		</div>

		<div class="grid grid-cols-1 gap-12 md:grid-cols-2 lg:grid-cols-3">
			{#each [{ title: 'The End of Mindless Transcription', cat: 'AI Research', date: 'Jan 24, 2026', author: 'Dr. Elena Rossi', color: 'from-blue-500 to-indigo-500' }, { title: 'How Visual Cues Enhance Semantic Recall', cat: 'UX Design', date: 'Jan 20, 2026', author: 'Sarah Miller', color: 'from-purple-500 to-pink-500' }, { title: 'Scaling Personalization for 50k Users', cat: 'Engineering', date: 'Jan 15, 2026', author: 'James Chen', color: 'from-blue-600 to-emerald-500' }] as post}
				<div class="group cursor-pointer">
					<div
						class="relative mb-8 aspect-[16/10] bg-gradient-to-br {post.color} overflow-hidden rounded-[2.5rem] shadow-lg transition-transform group-hover:scale-[0.98]"
					>
						<div
							class="absolute inset-0 bg-black/10 opacity-0 transition-opacity group-hover:opacity-100"
						></div>
						<div
							class="absolute bottom-6 left-6 rounded-full bg-white/20 px-4 py-1 text-xs font-bold tracking-widest text-white uppercase backdrop-blur-md"
						>
							{post.cat}
						</div>
					</div>
					<p
						class="mb-2 text-xs font-bold tracking-widest text-blue-600 uppercase dark:text-blue-400"
					>
						{post.date}
					</p>
					<h3
						class="mb-4 text-2xl leading-tight font-black text-gray-900 transition-colors group-hover:text-blue-600 dark:text-white"
					>
						{post.title}
					</h3>
					<div class="flex items-center gap-3">
						<div
							class="flex h-8 w-8 items-center justify-center rounded-full bg-gray-200 text-[10px] italic dark:bg-gray-800"
						>
							👤
						</div>
						<div class="text-sm font-medium text-gray-500 dark:text-gray-400">By {post.author}</div>
					</div>
				</div>
			{/each}
		</div>

		<!-- Newsletter Section -->
		<div
			class="relative mt-48 overflow-hidden rounded-[4rem] bg-gray-900 p-16 text-white shadow-2xl"
		>
			<div
				class="absolute inset-0 bg-[radial-gradient(circle_at_bottom_left,rgba(59,130,246,0.3),transparent)]"
			></div>
			<div class="relative z-10 grid grid-cols-1 items-center gap-16 lg:grid-cols-2">
				<div>
					<h3 class="mb-6 text-4xl leading-tight font-black">Stay ahead of <br />the curve.</h3>
					<p class="text-lg text-gray-400">
						Receive our monthly digest of education trends and Noteo updates directly in your inbox.
					</p>
				</div>
				<div class="flex flex-col gap-4 sm:flex-row">
					<input
						type="email"
						placeholder="you@university.edu"
						class="flex-grow rounded-2xl border border-white/20 bg-white/10 px-6 py-4 font-medium text-white transition-all outline-none placeholder:text-gray-500 focus:bg-white/20"
					/>
					<button
						class="rounded-2xl bg-white px-10 py-4 font-black text-gray-900 transition-all hover:scale-105 active:scale-95"
						>Subscribe</button
					>
				</div>
			</div>
		</div>
	</div>
</div>

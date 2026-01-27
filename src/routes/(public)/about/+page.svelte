<script lang="ts">
	import { onMount } from 'svelte';
	let mounted = $state(false);

	onMount(() => {
		mounted = true;
	});
</script>

<div class="overflow-hidden bg-white transition-colors duration-500 dark:bg-gray-950">
	<!-- Hero Section -->
	<section class="relative py-16 sm:py-24">
		<div class="relative mx-auto max-w-7xl px-6 lg:px-8">
			<div
				class="absolute -top-24 left-1/2 -z-10 h-[600px] w-full -translate-x-1/2 bg-gradient-to-b from-blue-50/50 to-transparent blur-3xl dark:from-blue-900/10"
			></div>

			<div
				class="mx-auto max-w-2xl text-center {mounted
					? 'translate-y-0 opacity-100'
					: 'translate-y-10 opacity-0'} transition-all duration-1000"
			>
				<h2 class="mb-4 text-xs font-bold tracking-widest text-blue-600 uppercase">The Project</h2>
				<h1
					class="mb-6 text-4xl font-black tracking-tight text-gray-900 sm:text-5xl dark:text-white"
				>
					Recent, <span
						class="bg-gradient-to-r from-blue-600 to-indigo-600 bg-clip-text text-transparent"
						>Free & Open Source</span
					>.
				</h1>
				<p class="text-base leading-7 font-medium text-gray-600 dark:text-gray-400">
					Noteo is a collaborative study project born from the desire to leverage modern AI to
					actually help students focus on listening rather than frantic writing.
				</p>
			</div>
		</div>
	</section>

	<!-- Study Project Content -->
	<section class="py-24 sm:py-32">
		<div class="mx-auto max-w-7xl px-6 lg:px-8">
			<div class="grid grid-cols-1 items-center gap-16 md:grid-cols-2">
				<div class="prose max-w-none prose-blue dark:prose-invert">
					<h2 class="mb-6 text-3xl font-black text-gray-900 dark:text-white">
						A Study Project with Heart
					</h2>
					<p class="mb-6 text-lg leading-relaxed text-gray-600 dark:text-gray-400">
						We started Noteo in 2026 as a practical investigation into human-AI collaboration in
						educational environments. Our goal isn't profit—it's understanding and accessibility.
					</p>
					<ul class="space-y-4">
						<li class="flex gap-3">
							<span class="font-bold text-blue-600">✓</span>
							<span class="text-gray-700 dark:text-gray-300">Entirely free for all students.</span>
						</li>
						<li class="flex gap-3">
							<span class="font-bold text-blue-600">✓</span>
							<span class="text-gray-700 dark:text-gray-300">Open-source codebase on GitHub.</span>
						</li>
						<li class="flex gap-3">
							<span class="font-bold text-blue-600">✓</span>
							<span class="text-gray-700 dark:text-gray-300">Peer-reviewed AI methodology.</span>
						</li>
					</ul>
				</div>
				<div
					class="relative flex aspect-video items-center justify-center rounded-3xl border border-gray-200 bg-gray-100 text-5xl font-black text-gray-300 italic shadow-inner dark:border-gray-800 dark:bg-gray-900 dark:text-gray-700"
				>
					COLLABORATIVE
				</div>
			</div>
		</div>
	</section>

	<!-- Open Source Collaboration -->
	<section class="bg-gray-50 py-32 dark:bg-gray-900/30">
		<div class="mx-auto max-w-7xl px-6 text-center lg:px-8">
			<h2 class="mb-8 text-3xl font-black text-gray-900 dark:text-white">Join the Collaboration</h2>
			<p class="mx-auto mb-12 max-w-2xl text-lg text-gray-600 dark:text-gray-400">
				Noteo is built on the shoulders of the open-source community. We welcome developers,
				educators, and students to contribute to the core engine, UI, or documentation.
			</p>

			<div class="grid grid-cols-1 gap-8 md:grid-cols-3">
				{#each [{ t: 'GitHub Repo', d: 'Check out the code, report bugs, or submit PRs.', i: '💻' }, { t: 'Discord Community', d: 'Discuss features and learning strategies.', i: '💬' }, { t: 'Documentation', d: 'Help us improve our guides and AI context rules.', i: '📚' }] as col}
					<div
						class="rounded-3xl border border-gray-100 bg-white p-10 transition-all hover:shadow-xl dark:border-gray-800 dark:bg-gray-950"
					>
						<div class="mb-4 text-4xl">{col.i}</div>
						<h3 class="mb-2 text-xl font-bold text-gray-900 dark:text-white">{col.t}</h3>
						<p class="text-sm text-gray-500 dark:text-gray-400">{col.d}</p>
					</div>
				{/each}
			</div>
		</div>
	</section>

	<!-- Call to Action Banner -->
	<section class="px-4 py-32 text-center">
		<div
			class="shadow-3xl mx-auto max-w-4xl rounded-[3rem] bg-blue-600 p-12 shadow-blue-500/30 sm:p-20 dark:bg-blue-700"
		>
			<h2 class="mb-8 text-3xl font-black text-white sm:text-4xl">Part of something bigger.</h2>
			<div class="flex flex-wrap justify-center gap-6">
				<a
					href="https://github.com"
					class="rounded-2xl bg-white px-10 py-5 font-black text-blue-600 transition-transform hover:scale-105"
					>Star on GitHub</a
				>
				<a
					href="/contact"
					class="rounded-2xl border-2 border-white px-10 py-5 font-black text-white transition-all hover:bg-white/10"
					>Support the Project</a
				>
			</div>
		</div>
	</section>
</div>

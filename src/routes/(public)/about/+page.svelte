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
				<h2 class="mb-4 text-xs font-bold tracking-widest text-blue-600 uppercase">Our Mission</h2>
				<h1
					class="mb-6 text-4xl font-black tracking-tight text-gray-900 sm:text-5xl dark:text-white"
				>
					Democratizing <span
						class="bg-gradient-to-r from-blue-600 to-indigo-600 bg-clip-text text-transparent"
						>Complex Knowledge</span
					>.
				</h1>
				<p class="text-base leading-7 font-medium text-gray-600 dark:text-gray-400">
					We're a team of educators and engineers dedicated to making learning more efficient,
					personalized, and accessible for everyone.
				</p>
			</div>
		</div>
	</section>

	<!-- Values Section -->
	<section class="bg-gray-50 py-32 dark:bg-gray-900/30">
		<div class="mx-auto max-w-7xl px-6 lg:px-8">
			<div class="grid grid-cols-1 gap-8 md:grid-cols-2 lg:grid-cols-4">
				{#each [{ t: 'Radical Simplicity', d: 'Turning complex theories into understandable insights.', i: '⚡' }, { t: 'Human-Centric AI', d: 'AI that empowers the user, never replaces the thinker.', i: '🤝' }, { t: 'Universal Access', d: 'Built for every language, subject, and student level.', i: '🌍' }, { t: 'Data Sovereignty', d: 'Your thoughts, your notes, your absolute privacy.', i: '🛡️' }] as value}
					<div
						class="rounded-[2.5rem] border border-gray-100 bg-white p-10 transition-all hover:scale-105 hover:shadow-2xl hover:shadow-blue-500/10 dark:border-gray-800 dark:bg-gray-950"
					>
						<div class="mb-6 text-5xl">{value.i}</div>
						<h3 class="mb-4 text-xl font-bold text-gray-900 dark:text-white">{value.t}</h3>
						<p class="text-sm leading-relaxed text-gray-600 dark:text-gray-400">{value.d}</p>
					</div>
				{/each}
			</div>
		</div>
	</section>

	<!-- Journey Timeline -->
	<section class="py-32">
		<div class="mx-auto max-w-7xl px-6 lg:px-8">
			<div class="mb-24 text-center">
				<h2 class="mb-4 text-4xl font-black text-gray-900 dark:text-white">Our Journey</h2>
				<p class="text-gray-500">From a dorm room idea to a global platform.</p>
			</div>

			<div class="relative mx-auto max-w-4xl">
				<!-- Timeline line -->
				<div
					class="absolute top-0 left-1/2 h-full w-0.5 -translate-x-1/2 bg-blue-100 dark:bg-blue-900/50"
				></div>

				<div class="space-y-24">
					{#each [{ year: '2023', event: 'The Spark', desc: 'Noteo was founded after a group of NLP researchers saw students struggling with remote learning fatigue.', side: 'left' }, { year: '2024', event: 'v1.0 Launch', desc: 'Our first 1,000 users joined, providing feedback that shaped our unique context-aware engine.', side: 'right' }, { year: '2025', event: 'Expansion', desc: 'Noteo integrated with major LMS platforms and hit 50,000 active quarterly users.', side: 'left' }, { year: 'Now', event: 'The Future', desc: 'Deploying advanced multimodal support to understand diagrams and live audio perfectly.', side: 'right' }] as item}
						<div class="relative flex items-center justify-center">
							<div
								class="absolute left-1/2 h-6 w-6 -translate-x-1/2 rounded-full bg-blue-600 ring-8 ring-blue-50 dark:ring-blue-900/30"
							></div>

							<div class="grid w-full grid-cols-2 gap-12">
								<div
									class={item.side === 'left'
										? 'text-right'
										: 'col-start-2 font-black text-blue-600 italic'}
								>
									{#if item.side === 'left'}
										<div class="mb-2 text-3xl font-black text-gray-900 dark:text-white">
											{item.year}
										</div>
										<h4 class="mb-2 text-xl font-bold text-blue-600">{item.event}</h4>
										<p class="text-gray-600 dark:text-gray-400">{item.desc}</p>
									{:else}
										<div class="text-2xl font-black tracking-widest">{item.year}</div>
									{/if}
								</div>
								<div
									class={item.side === 'right'
										? 'text-left'
										: 'col-start-1 text-right font-black text-blue-600 italic'}
								>
									{#if item.side === 'right'}
										<div class="mb-2 text-3xl font-black text-gray-900 dark:text-white">
											{item.year}
										</div>
										<h4 class="mb-2 text-xl font-bold text-blue-600">{item.event}</h4>
										<p class="text-gray-600 dark:text-gray-400">{item.desc}</p>
									{:else}
										<div class="text-2xl font-black tracking-widest">{item.year}</div>
									{/if}
								</div>
							</div>
						</div>
					{/each}
				</div>
			</div>
		</div>
	</section>

	<!-- Team Section -->
	<section class="bg-gray-50 py-32 dark:bg-gray-900/30">
		<div class="mx-auto max-w-7xl px-6 lg:px-8">
			<div class="mb-24 text-center">
				<h2 class="mb-8 text-4xl font-black text-gray-900 dark:text-white">Meet the Dreamers</h2>
				<p class="mx-auto max-w-2xl text-lg text-gray-600 italic dark:text-gray-400">
					"Behind every AI enhancement is a human intent to understand better."
				</p>
			</div>

			<div class="grid grid-cols-1 gap-12 sm:grid-cols-2 lg:grid-cols-3">
				{#each [{ name: 'Dr. Elena Rossi', role: 'Head of AI Research', desc: 'Former Stanford Fellow specializing in natural language understanding.' }, { name: 'James Chen', role: 'Founder & CEO', desc: 'Passionate about bridging the gap between tech and traditional education.' }, { name: 'Sarah Miller', role: 'Chief Design Officer', desc: 'Focused on creating seamless, invisible technology experiences.' }] as member}
					<div class="group">
						<div
							class="relative mb-8 aspect-[4/5] overflow-hidden rounded-3xl bg-gray-200 transition-all group-hover:scale-[0.98] dark:bg-gray-800"
						>
							<div
								class="absolute inset-0 bg-gradient-to-t from-blue-900 via-transparent to-transparent opacity-0 transition-opacity group-hover:opacity-60"
							></div>
							<div
								class="absolute bottom-6 left-6 translate-y-4 text-white opacity-0 transition-all group-hover:translate-y-0 group-hover:opacity-100"
							>
								<p class="text-sm font-medium">Follow on LinkedIn →</p>
							</div>
							<!-- Placeholder for Avatar -->
							<div
								class="flex h-full w-full items-center justify-center text-8xl grayscale transition-all group-hover:grayscale-0"
							>
								👤
							</div>
						</div>
						<h4 class="mb-1 text-2xl font-bold text-gray-900 dark:text-white">{member.name}</h4>
						<p class="mb-3 text-sm font-semibold text-blue-600">{member.role}</p>
						<p class="text-sm text-gray-600 dark:text-gray-400">{member.desc}</p>
					</div>
				{/each}
			</div>
		</div>
	</section>

	<!-- Call to Action Banner -->
	<section class="px-4 py-32">
		<div
			class="shadow-3xl mx-auto max-w-4xl rounded-[3rem] bg-blue-600 p-12 text-center shadow-blue-500/30 sm:p-20 dark:bg-blue-700"
		>
			<h2 class="mb-8 text-3xl font-black text-white sm:text-4xl">
				Ready to start your own journey with us?
			</h2>
			<div class="flex flex-wrap justify-center gap-6">
				<a
					href="/jobs"
					class="rounded-2xl bg-white px-10 py-5 font-black text-blue-600 transition-transform hover:scale-105"
					>View Open Roles</a
				>
				<a
					href="/contact"
					class="rounded-2xl border-2 border-white px-10 py-5 font-black text-white transition-all hover:bg-white/10"
					>Get in Touch</a
				>
			</div>
		</div>
	</section>
</div>

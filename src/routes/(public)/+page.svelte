<script lang="ts">
	import { onMount } from 'svelte';
	let mounted = $state(false);

	onMount(() => {
		mounted = true;
	});
</script>

<div class="relative isolate overflow-hidden">
	<!-- Hyper Advanced Animated Background -->
	<div class="absolute inset-0 -z-10 bg-white transition-colors duration-500 dark:bg-gray-950">
		<div
			class="absolute inset-0 opacity-20 dark:opacity-10"
			style="background-image: radial-gradient(#3b82f6 1px, transparent 1px); background-size: 40px 40px;"
		></div>
		<div
			class="absolute top-0 right-0 h-[600px] w-[600px] translate-x-1/2 -translate-y-1/2 animate-pulse rounded-full bg-blue-400/20 blur-[120px] dark:bg-blue-600/10"
		></div>
		<div
			class="absolute bottom-0 left-0 h-[500px] w-[500px] -translate-x-1/2 translate-y-1/2 animate-pulse rounded-full bg-indigo-400/20 blur-[100px] dark:bg-indigo-600/10"
			style="animation-delay: 2s"
		></div>
	</div>

	<!-- Hero Section -->
	<section class="relative pt-16 pb-20 sm:pt-20 sm:pb-32">
		<div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
			<div
				class="text-center {mounted
					? 'translate-y-0 opacity-100'
					: 'translate-y-10 opacity-0'} transition-all duration-1000"
			>
				<div
					class="mb-6 inline-flex items-center gap-2 rounded-full border border-blue-100 bg-blue-50 px-4 py-2 text-xs font-medium text-blue-700 dark:border-blue-800 dark:bg-blue-900/30 dark:text-blue-300"
				>
					<span class="relative flex h-2 w-2">
						<span
							class="absolute inline-flex h-full w-full animate-ping rounded-full bg-blue-400 opacity-75"
						></span>
						<span class="relative inline-flex h-2 w-2 rounded-full bg-blue-500"></span>
					</span>
					Now with GPT-4 Omni Support
				</div>
				<h1
					class="mx-auto max-w-4xl text-5xl leading-[1.15] font-black tracking-tight text-gray-900 sm:text-6xl dark:text-white"
				>
					Note the <span
						class="bg-gradient-to-r from-blue-600 via-indigo-500 to-purple-600 bg-clip-text text-transparent"
						>Essential</span
					>. <br />Let AI handle the Depth.
				</h1>
				<p class="mx-auto mt-6 max-w-xl text-lg leading-relaxed text-gray-600 dark:text-gray-400">
					Focus on the speaker, not the keyboard. Capture key points during live sessions and let
					Noteo's intelligence complete the rest on demand.
				</p>
				<div class="mt-12 flex flex-col items-center justify-center gap-6 sm:flex-row">
					<a
						href="/signup"
						class="group relative flex items-center gap-2 overflow-hidden rounded-2xl bg-blue-600 px-10 py-5 font-bold text-white shadow-2xl shadow-blue-500/40 transition-all hover:scale-105 hover:bg-blue-700 active:scale-95"
					>
						<div
							class="absolute inset-0 -translate-x-full bg-gradient-to-r from-white/0 via-white/20 to-white/0 transition-transform duration-1000 group-hover:translate-x-full"
						></div>
						Get Started Free
						<svg
							class="h-5 w-5 transition-transform group-hover:translate-x-1"
							fill="none"
							viewBox="0 0 24 24"
							stroke="currentColor"
							><path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M13 7l5 5m0 0l-5 5m5-5H6"
							/></svg
						>
					</a>
					<a
						href="#how"
						class="flex items-center gap-2 font-semibold text-gray-900 transition-colors hover:text-blue-600 dark:text-gray-300 dark:hover:text-blue-400"
					>
						Watch Demo
						<span
							class="flex h-10 w-10 items-center justify-center rounded-full border border-gray-200 bg-white shadow-sm dark:border-gray-800 dark:bg-gray-900"
							><svg class="h-4 w-4" fill="currentColor" viewBox="0 0 20 20"
								><path
									fill-rule="evenodd"
									d="M10 18a8 8 0 100-16 8 8 0 000 16zM9.555 7.168A1 1 0 008 8v4a1 1 0 001.555.832l3-2a1 1 0 000-1.664l-3-2z"
									clip-rule="evenodd"
								/></svg
							></span
						>
					</a>
				</div>
			</div>
		</div>
	</section>

	<!-- How it Works -->
	<section id="how" class="bg-white py-32 dark:bg-gray-950">
		<div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
			<div class="mb-24 text-center">
				<h2 class="mb-4 text-sm font-bold tracking-widest text-blue-600 uppercase">The Process</h2>
				<h3 class="text-4xl font-extrabold text-gray-900 sm:text-5xl dark:text-white">
					From fragment to perfection
				</h3>
			</div>

			<div class="relative grid grid-cols-1 gap-12 md:grid-cols-3">
				<!-- Connector line (desktop) -->
				<div
					class="absolute top-1/2 left-0 -z-10 hidden h-0.5 w-full translate-y-[-50%] bg-gray-100 md:block dark:bg-gray-800"
				></div>

				{#each [{ step: '01', title: 'Identify', desc: 'Note down only the core concepts and unique insights as they happen in real-time.', icon: '✍️' }, { step: '02', title: 'Request', desc: 'Simply ask the AI to expand on definitions or provide complex examples for your fragments.', icon: '🧠' }, { step: '03', title: 'Integrate', desc: 'Review a complete, high-fidelity set of notes that feels like you wrote every word.', icon: '🚀' }] as item}
					<div
						class="relative rounded-3xl border border-gray-100 bg-white p-8 shadow-xl shadow-gray-200/50 transition-transform hover:-translate-y-2 dark:border-gray-800 dark:bg-gray-900 dark:shadow-none"
					>
						<div
							class="absolute -top-6 left-8 text-5xl font-black text-gray-100 dark:text-gray-800"
						>
							{item.step}
						</div>
						<div class="mb-6 text-4xl">{item.icon}</div>
						<h4 class="mb-4 text-2xl font-bold text-gray-900 dark:text-white">{item.title}</h4>
						<p class="leading-relaxed text-gray-600 dark:text-gray-400">{item.desc}</p>
					</div>
				{/each}
			</div>
		</div>
	</section>

	<!-- Features Deep Dive -->
	<section class="relative overflow-hidden py-32">
		<div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
			<div class="grid grid-cols-1 items-center gap-24 lg:grid-cols-2">
				<div>
					<h2 class="mb-8 text-4xl leading-tight font-black text-gray-900 dark:text-white">
						Not just notes.<br />
						<span class="text-blue-600">A second brain.</span>
					</h2>
					<div class="space-y-10">
						{#each [{ t: 'Smart Context Enrichment', d: 'Automatically links relevant research papers and academic sources to your notes.', c: 'bg-blue-100 dark:bg-blue-900/40 text-blue-600' }, { t: 'Diagram generation', d: 'Converts complex technical descriptions into beautiful Mermaid or SVG diagrams.', c: 'bg-purple-100 dark:bg-purple-900/40 text-purple-600' }, { t: 'Collaboration Sync', d: 'Share your AI-enhanced notes with classmates and see their comments in real-time.', c: 'bg-indigo-100 dark:bg-indigo-900/40 text-indigo-600' }] as feature}
							<div class="flex gap-6">
								<div
									class="h-10 w-10 flex-shrink-0 rounded-xl {feature.c} flex items-center justify-center font-bold"
								>
									✓
								</div>
								<div>
									<h4 class="mb-2 text-xl font-bold text-gray-900 dark:text-white">{feature.t}</h4>
									<p class="text-gray-600 dark:text-gray-400">{feature.d}</p>
								</div>
							</div>
						{/each}
					</div>
				</div>
				<div class="relative">
					<div
						class="absolute -inset-4 rounded-3xl bg-gradient-to-tr from-blue-500 to-purple-500 opacity-20 blur-2xl"
					></div>
					<div
						class="relative aspect-square overflow-hidden rounded-2xl border border-gray-100 bg-white shadow-2xl dark:border-gray-800 dark:bg-gray-900"
					>
						<!-- Creative Mockup -->
						<div class="flex h-full flex-col p-8">
							<div class="mb-8 flex items-center justify-between">
								<div class="flex gap-2">
									<div class="h-3 w-3 rounded-full bg-red-400"></div>
									<div class="h-3 w-3 rounded-full bg-yellow-400"></div>
									<div class="h-3 w-3 rounded-full bg-green-400"></div>
								</div>
								<div
									class="rounded-full bg-gray-100 px-3 py-1 text-[10px] font-bold tracking-widest text-gray-400 uppercase dark:bg-gray-800"
								>
									Lecture.noteo
								</div>
							</div>
							<div class="flex-grow space-y-4">
								<div class="h-4 w-3/4 rounded-full bg-gray-100 dark:bg-gray-800"></div>
								<div class="h-4 w-full rounded-full bg-gray-100 dark:bg-gray-800"></div>
								<div class="h-4 w-5/6 rounded-full bg-gray-100 dark:bg-gray-800"></div>
								<div
									class="my-8 rounded-2xl border border-blue-100 bg-blue-50/50 p-6 dark:border-blue-900/30 dark:bg-blue-900/20"
								>
									<div class="mb-2 text-sm font-bold text-blue-600 italic">
										Quantum Entanglement
									</div>
									<div class="mb-4 text-xs leading-relaxed text-blue-800 dark:text-blue-200">
										A physical phenomenon that occurs when a group of particles are generated,
										interact, or share spatial proximity...
									</div>
									<div class="grid grid-cols-2 gap-2">
										<div class="h-16 rounded-lg bg-blue-100 dark:bg-blue-800"></div>
										<div class="h-16 rounded-lg bg-indigo-100 dark:bg-indigo-800"></div>
									</div>
								</div>
								<div class="h-4 w-full rounded-full bg-gray-100 dark:bg-gray-800"></div>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Open Source Section -->
	<section id="open-source" class="bg-gray-50 py-32 dark:bg-gray-900/30">
		<div class="mx-auto max-w-7xl px-4 text-center">
			<div
				class="mb-6 inline-flex items-center gap-2 rounded-full bg-green-100 px-3 py-1 text-xs font-bold text-green-700 uppercase dark:bg-green-900/30 dark:text-green-300"
			>
				100% Free & Open Source
			</div>
			<h2 class="mb-6 text-4xl font-black text-balance text-gray-900 dark:text-white">
				Built by the community, <br />for the community.
			</h2>
			<p class="mx-auto mb-12 max-w-2xl text-lg text-gray-600 dark:text-gray-400">
				Noteo is a study project dedicated to making education more accessible. We believe that
				learning tools should be free, open, and collaborative.
			</p>
			<div class="flex justify-center gap-4">
				<a
					href="https://github.com"
					class="flex items-center gap-3 rounded-2xl bg-gray-900 px-8 py-4 font-bold text-white transition-all hover:scale-105 dark:bg-white dark:text-gray-900"
				>
					<svg class="h-6 w-6" fill="currentColor" viewBox="0 0 24 24"
						><path
							fill-rule="evenodd"
							d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z"
							clip-rule="evenodd"
						/></svg
					>
					Star on GitHub
				</a>
			</div>
		</div>
	</section>

	<!-- Testimonials -->
	<section class="py-32">
		<div class="mx-auto max-w-7xl px-4">
			<div class="grid grid-cols-1 gap-8 md:grid-cols-2 lg:grid-cols-3">
				{#each [{ name: 'Sarah Jenkins', role: 'Medical Student', text: "Noteo saved me during anatomy finals. The AI explained complex physiological processes in ways my textbook couldn't.", avatar: 'SJ' }, { name: 'Dr. Marcus Lee', role: 'University Professor', text: "I recommend Noteo to all my students. It helps them engage more in class because they aren't frantically scribbling.", avatar: 'ML' }, { name: 'Alex Rivera', role: 'Software Engineer', text: 'Even for professional documentation, Noteo is incredible. It turns my meeting notes into structured specs.', avatar: 'AR' }] as t}
					<div
						class="rounded-3xl border border-gray-100 bg-gray-50 p-8 dark:border-gray-800 dark:bg-gray-900/50"
					>
						<div class="mb-6 flex gap-1 font-bold text-yellow-400">★★★★★</div>
						<p class="mb-8 leading-relaxed text-gray-600 italic dark:text-gray-300">"{t.text}"</p>
						<div class="flex items-center gap-4">
							<div
								class="flex h-10 w-10 items-center justify-center rounded-full bg-blue-600 font-bold text-white"
							>
								{t.avatar}
							</div>
							<div>
								<div class="font-bold text-gray-900 dark:text-white">{t.name}</div>
								<div class="text-xs font-medium text-blue-600">{t.role}</div>
							</div>
						</div>
					</div>
				{/each}
			</div>
		</div>
	</section>

	<!-- CTA -->
	<section class="py-32">
		<div class="mx-auto max-w-7xl px-4">
			<div class="relative overflow-hidden rounded-[3rem] bg-blue-600 p-12 text-center sm:p-24">
				<div
					class="absolute inset-0 bg-[radial-gradient(circle_at_top_right,rgba(255,255,255,0.2),transparent)]"
				></div>
				<h2 class="relative mb-8 text-4xl leading-tight font-black text-white sm:text-6xl">
					Ready to revolutionize your <br />note-taking?
				</h2>
				<p class="relative mx-auto mb-12 max-w-2xl text-lg text-blue-100 italic">
					Join 50,000+ students already using Noteo to master their education.
				</p>
				<a
					href="/signup"
					class="relative inline-flex rounded-2xl bg-white px-12 py-5 font-black text-blue-600 shadow-xl transition-transform hover:scale-105 active:scale-95"
				>
					Start for Free Today
				</a>
			</div>
		</div>
	</section>
</div>

<style>
	@keyframes pulse {
		0%,
		100% {
			opacity: 0.2;
			transform: scale(1);
		}
		50% {
			opacity: 0.4;
			transform: scale(1.1);
		}
	}
	.animate-pulse {
		animation: pulse 10s infinite;
	}
</style>

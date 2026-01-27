<script lang="ts">
	let formState = $state({ name: '', email: '', message: '' });
</script>

<div
	class="relative isolate flex min-h-[calc(100vh-64px)] items-center overflow-hidden py-12 sm:py-16"
>
	<!-- Decorative background -->
	<div class="absolute inset-0 -z-10 bg-white transition-colors duration-500 dark:bg-gray-950">
		<div
			class="absolute inset-x-0 -top-40 -z-10 transform-gpu overflow-hidden blur-3xl sm:-top-80"
			aria-hidden="true"
		>
			<div
				class="relative left-[calc(50%-11rem)] aspect-[1155/678] w-[36.125rem] -translate-x-1/2 rotate-[30deg] bg-gradient-to-tr from-[#3b82f6] to-[#818cf8] opacity-20 sm:left-[calc(50%-30rem)] sm:w-[72.1875rem]"
				style="clip-path: polygon(74.1% 44.1%, 100% 61.6%, 97.5% 26.9%, 85.5% 0.1%, 80.7% 2%, 72.5% 32.5%, 60.2% 62.4%, 52.4% 68.1%, 47.5% 58.3%, 45.2% 34.5%, 27.5% 76.7%, 0.1% 64.9%, 17.9% 100%, 27.6% 76.8%, 76.1% 97.7%, 74.1% 44.1%)"
			></div>
		</div>
	</div>

	<div class="mx-auto max-w-7xl px-6 lg:px-8">
		<div class="grid grid-cols-1 items-center gap-24 lg:grid-cols-2">
			<!-- Contact Content -->
			<div>
				<h2 class="mb-6 text-[10px] font-bold tracking-widest text-blue-600 uppercase">
					Contact Us
				</h2>
				<h1 class="mb-6 text-3xl font-black text-gray-900 sm:text-5xl dark:text-white">
					Let's <span class="text-blue-600">talk</span>.
				</h1>
				<p class="mb-10 max-w-sm text-base text-gray-600 dark:text-gray-400">
					Whether you have a feature suggestion, found a bug, or want to collaborate on this
					open-source project, we'd love to hear from you.
				</p>

				<div class="space-y-8">
					<div class="flex gap-4">
						<div
							class="flex h-12 w-12 items-center justify-center rounded-2xl bg-blue-50 text-xl italic shadow-sm dark:bg-blue-900/30"
						>
							✉️
						</div>
						<div>
							<h3 class="font-bold text-gray-900 dark:text-white">Email</h3>
							<p class="text-blue-600">hello@noteo.inc</p>
						</div>
					</div>
					<div class="flex gap-4">
						<div
							class="flex h-12 w-12 items-center justify-center rounded-2xl bg-blue-50 text-xl italic shadow-sm dark:bg-blue-900/30"
						>
							🐙
						</div>
						<div>
							<h3 class="font-bold text-gray-900 dark:text-white">Open Source</h3>
							<p class="text-blue-600">github.com/noteo/core</p>
						</div>
					</div>
				</div>
			</div>

			<!-- Contact Form (Glassmorphism) -->
			<div class="relative">
				<div
					class="absolute -inset-4 rounded-3xl bg-gradient-to-tr from-blue-500 to-indigo-500 opacity-10 blur-2xl"
				></div>
				<div
					class="relative rounded-[2.5rem] border border-white/20 bg-white/70 p-6 shadow-2xl backdrop-blur-xl sm:p-8 dark:border-white/10 dark:bg-gray-900/70"
				>
					<form action="#" method="POST" class="space-y-4">
						<div>
							<label
								for="name"
								class="mb-1.5 ml-1 block text-xs font-bold text-gray-900 dark:text-white"
								>Full Name</label
							>
							<input
								type="text"
								id="name"
								bind:value={formState.name}
								class="w-full rounded-xl border border-gray-100 bg-white px-5 py-3 text-sm transition-all outline-none focus:border-transparent focus:ring-2 focus:ring-blue-600 dark:border-gray-800 dark:bg-gray-950"
								placeholder="Your name"
							/>
						</div>
						<div>
							<label
								for="email"
								class="mb-1.5 ml-1 block text-xs font-bold text-gray-900 dark:text-white"
								>Email Address</label
							>
							<input
								type="email"
								id="email"
								bind:value={formState.email}
								class="w-full rounded-xl border border-gray-100 bg-white px-5 py-3 text-sm transition-all outline-none focus:border-transparent focus:ring-2 focus:ring-blue-600 dark:border-gray-800 dark:bg-gray-950"
								placeholder="you@example.com"
							/>
						</div>
						<div>
							<label
								for="message"
								class="mb-1.5 ml-1 block text-xs font-bold text-gray-900 dark:text-white"
								>Message</label
							>
							<textarea
								id="message"
								rows="3"
								bind:value={formState.message}
								class="w-full rounded-xl border border-gray-100 bg-white px-5 py-3 text-sm transition-all outline-none focus:border-transparent focus:ring-2 focus:ring-blue-600 dark:border-gray-800 dark:bg-gray-950"
								placeholder="How can we help?"
							></textarea>
						</div>
						<button
							type="submit"
							class="flex w-full items-center justify-center gap-2 rounded-xl bg-blue-600 py-4 text-sm font-black text-white shadow-xl shadow-blue-500/20 transition-all hover:scale-[1.01] hover:bg-blue-700 active:scale-95"
						>
							Send Message
							<svg class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor"
								><path
									stroke-linecap="round"
									stroke-linejoin="round"
									stroke-width="2"
									d="M14 5l7 7m0 0l-7 7m7-7H3"
								/></svg
							>
						</button>
					</form>
				</div>
			</div>
		</div>
	</div>
</div>

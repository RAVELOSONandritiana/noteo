<script lang="ts">
	import ThemeToggle from '$lib/components/ThemeToggle.svelte';
	import { page } from '$app/state';

	const { children } = $props();

	const navLinks = [
		{ href: '/', label: 'Home' },
		{ href: '/about', label: 'About' },
		{ href: '/contact', label: 'Contact' }
	];

	function isActive(path: string) {
		return page.url.pathname === path;
	}
</script>

<div
	class="flex min-h-screen flex-col bg-white font-sans text-gray-900 transition-colors duration-300 dark:bg-gray-950 dark:text-gray-100"
>
	<!-- Navigation -->
	<header
		class="sticky top-0 z-50 w-full border-b border-gray-200 bg-white/80 backdrop-blur-md dark:border-gray-800 dark:bg-gray-950/80"
	>
		<div class="mx-auto flex h-16 max-w-7xl items-center justify-between px-4 sm:px-6 lg:px-8">
			<a href="/" class="flex items-center gap-2 transition-opacity hover:opacity-80">
				<div
					class="flex h-8 w-8 items-center justify-center rounded-lg bg-blue-600 font-bold text-white shadow-lg shadow-blue-500/20"
				>
					N
				</div>
				<span class="text-xl font-bold tracking-tight">Noteo</span>
			</a>

			<nav class="hidden items-center gap-8 md:flex">
				{#each navLinks as link}
					<a
						href={link.href}
						class="text-sm font-medium transition-colors hover:text-blue-600 dark:hover:text-blue-400 {isActive(
							link.href
						)
							? 'text-blue-600 dark:text-blue-400'
							: 'text-gray-600 dark:text-gray-400'}"
					>
						{link.label}
					</a>
				{/each}
			</nav>

			<div class="flex items-center gap-4">
				<ThemeToggle />
				<a
					href="/signup"
					class="hidden items-center justify-center rounded-full bg-blue-600 px-6 py-2 text-sm font-semibold text-white transition-all hover:bg-blue-700 hover:shadow-lg hover:shadow-blue-500/30 focus:ring-2 focus:ring-blue-500 focus:ring-offset-2 focus:outline-none active:scale-95 sm:inline-flex"
				>
					Get Started
				</a>
				<!-- Mobile menu button -->
				<button class="p-2 text-gray-500 md:hidden dark:text-gray-400">
					<svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M4 6h16M4 12h16M4 18h16"
						/>
					</svg>
				</button>
			</div>
		</div>
	</header>

	<!-- Main Content -->
	<main class="flex-grow">
		{@render children()}
	</main>

	<!-- Advanced Footer -->
	<footer
		class="border-t border-gray-200 bg-white/50 backdrop-blur-sm dark:border-gray-800 dark:bg-gray-950/50"
	>
		<div class="mx-auto max-w-7xl px-4 py-16 sm:px-6 lg:px-8">
			<div class="mb-16 grid grid-cols-1 gap-12 lg:grid-cols-12">
				<!-- Brand & Newsletter -->
				<div class="lg:col-span-5">
					<div class="mb-6 flex items-center gap-2">
						<div
							class="flex h-10 w-10 items-center justify-center rounded-xl bg-blue-600 font-bold text-white shadow-lg shadow-blue-500/20"
						>
							N
						</div>
						<span
							class="bg-gradient-to-r from-gray-900 to-gray-600 bg-clip-text text-2xl font-bold tracking-tight text-transparent dark:from-white dark:to-gray-400"
							>Noteo</span
						>
					</div>
					<p class="mb-8 max-w-sm text-sm leading-relaxed text-gray-600 dark:text-gray-400">
						Empowering the next generation of learners with world-class AI note-taking tools. Join
						our community of 50,000+ students and professionals.
					</p>

					<div class="max-w-md">
						<h3 class="mb-4 text-xs font-bold tracking-widest text-blue-600 uppercase">
							Join our Newsletter
						</h3>
						<form class="flex gap-2">
							<input
								type="email"
								placeholder="you@example.com"
								class="flex-grow rounded-xl border border-gray-200 bg-white px-4 py-3 text-sm focus:border-blue-600 focus:ring-0 dark:border-gray-800 dark:bg-gray-900 dark:text-white"
							/>
							<button
								class="rounded-xl bg-blue-600 px-6 py-3 text-sm font-bold text-white transition-colors hover:bg-blue-700"
							>
								Join
							</button>
						</form>
						<p class="mt-3 text-[10px] text-gray-400">
							Weekly tips on learning and productivity. No spam, ever.
						</p>
					</div>
				</div>

				<!-- Links Grid -->
				<div class="grid grid-cols-2 gap-8 sm:grid-cols-3 lg:col-span-7">
					<div>
						<h3
							class="mb-6 text-sm font-bold tracking-wider text-gray-900 uppercase dark:text-white"
						>
							Product
						</h3>
						<ul class="space-y-4">
							{#each [{ n: 'Features', h: '/features' }, { n: 'AI Capabilities', h: '/ai-capabilities' }, { n: 'Desktop App', h: '#' }, { n: 'Mobile (Beta)', h: '#' }] as link}
								<li>
									<a
										href={link.h}
										class="text-sm text-gray-500 transition-colors hover:text-blue-600 dark:text-gray-400 dark:hover:text-blue-200"
										>{link.n}</a
									>
								</li>
							{/each}
						</ul>
					</div>
					<div>
						<h3
							class="mb-6 text-sm font-bold tracking-wider text-gray-900 uppercase dark:text-white"
						>
							Company
						</h3>
						<ul class="space-y-4">
							{#each [{ n: 'About Us', h: '/about' }, { n: 'Our Vision', h: '/our-vision' }, { n: 'Careers', h: '/careers' }, { n: 'Contact', h: '/contact' }, { n: 'Blog', h: '/blog' }] as link}
								<li>
									<a
										href={link.h}
										class="text-sm text-gray-500 transition-colors hover:text-blue-600 dark:text-gray-400 dark:hover:text-blue-200"
										>{link.n}</a
									>
								</li>
							{/each}
						</ul>
					</div>
					<div>
						<h3
							class="mb-6 text-sm font-bold tracking-wider text-gray-900 uppercase dark:text-white"
						>
							Resources
						</h3>
						<ul class="space-y-4">
							{#each [{ n: 'Help Center', h: '/help-center' }, { n: 'API Docs', h: '/api-docs' }, { n: 'Security', h: '/security' }, { n: 'Privacy Policy', h: '/privacy-policy' }, { n: 'Terms of Service', h: '/terms-of-service' }] as link}
								<li>
									<a
										href={link.h}
										class="text-sm text-gray-500 transition-colors hover:text-blue-600 dark:text-gray-400 dark:hover:text-blue-200"
										>{link.n}</a
									>
								</li>
							{/each}
						</ul>
					</div>
				</div>
			</div>

			<!-- Bottom Bar -->
			<div
				class="mt-12 flex flex-col items-center justify-between gap-8 border-t border-gray-100 pt-12 md:flex-row dark:border-gray-800"
			>
				<div class="flex flex-col items-center gap-4 md:items-start">
					<p class="text-sm font-medium text-gray-400">
						© {new Date().getFullYear()} Noteo Inc. All rights reserved.
					</p>
					<div class="flex items-center gap-4">
						<div class="flex -space-x-2">
							{#each [1, 2, 3] as _}
								<div
									class="flex h-6 w-6 items-center justify-center rounded-full border-2 border-white bg-gray-200 text-[10px] font-bold dark:border-gray-950 dark:bg-gray-800"
								>
									👤
								</div>
							{/each}
						</div>
						<span class="text-[10px] font-bold tracking-widest text-gray-400 uppercase"
							>+ 50k Users</span
						>
					</div>
				</div>

				<div class="flex items-center gap-8">
					<div class="flex items-center gap-2">
						<span class="relative flex h-2 w-2">
							<span
								class="absolute inline-flex h-full w-full animate-ping rounded-full bg-green-400 opacity-75"
							></span>
							<span class="relative inline-flex h-2 w-2 rounded-full bg-green-500"></span>
						</span>
						<span
							class="text-xs font-bold tracking-tighter text-gray-500 uppercase dark:text-gray-400"
							>Status: Operational</span
						>
					</div>
					<div class="flex gap-4">
						{#each [{ n: 'X', d: 'M13.6823 10.6218L20.2391 3H18.6854L13.0184 9.61338L8.45524 3H3.21094L10.101 13.0645L3.21094 21H4.76465L10.7646 14.0729L15.6177 21H20.862L13.6821 10.6218H13.6823Z' }, { n: 'GH', d: 'M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z' }] as icon}
							<a
								href="#"
								class="flex h-8 w-8 items-center justify-center rounded-lg bg-gray-100 text-gray-500 transition-colors hover:text-blue-600 dark:bg-gray-800"
							>
								<svg class="h-4 w-4" fill="currentColor" viewBox="0 0 24 24"
									><path d={icon.d} /></svg
								>
							</a>
						{/each}
					</div>
				</div>
			</div>
		</div>
	</footer>
</div>

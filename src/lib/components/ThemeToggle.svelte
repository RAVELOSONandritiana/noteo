<script lang="ts">
	import { onMount } from 'svelte';

	let isDark = $state(false);

	onMount(() => {
		// Sync the state with the actual document class (set by app.html or previous toggle)
		isDark = document.documentElement.classList.contains('dark');
	});

	function toggleTheme() {
		isDark = !isDark;
		if (isDark) {
			document.documentElement.classList.add('dark');
			localStorage.setItem('theme', 'dark');
		} else {
			document.documentElement.classList.remove('dark');
			localStorage.setItem('theme', 'light');
		}
	}
</script>

<button
	onclick={toggleTheme}
	class="group relative inline-flex h-10 w-10 items-center justify-center rounded-xl border border-transparent bg-gray-100/50 transition-all hover:bg-gray-200/50 active:scale-90 dark:border-gray-700/50 dark:bg-gray-800/50 dark:hover:bg-gray-700/50"
	aria-label="Toggle theme"
>
	<div class="relative h-5 w-5 overflow-hidden">
		<!-- Sun Icon -->
		<div
			class="absolute inset-0 transform transition-transform duration-500 {isDark
				? 'translate-y-8 opacity-0'
				: 'translate-y-0 opacity-100'}"
		>
			<svg
				fill="none"
				viewBox="0 0 24 24"
				stroke-width="2"
				stroke="currentColor"
				class="h-5 w-5 text-amber-500"
			>
				<path
					stroke-linecap="round"
					stroke-linejoin="round"
					d="M12 3v2.25m6.364.386l-1.591 1.591M21 12h-2.25m-.386 6.364l-1.591-1.591M12 18.75V21m-4.773-4.227l-1.591 1.591M3 12h2.25m.386-6.364l1.591 1.591M15.75 12a3.75 3.75 0 11-7.5 0 3.75 3.75 0 017.5 0z"
				/>
			</svg>
		</div>
		<!-- Moon Icon -->
		<div
			class="absolute inset-0 transform transition-transform duration-500 {isDark
				? 'translate-y-0 opacity-100'
				: '-translate-y-8 opacity-0'}"
		>
			<svg
				fill="none"
				viewBox="0 0 24 24"
				stroke-width="2"
				stroke="currentColor"
				class="h-5 w-5 text-blue-400"
			>
				<path
					stroke-linecap="round"
					stroke-linejoin="round"
					d="M21.752 15.002A9.718 9.718 0 0118 15.75c-5.385 0-9.75-4.365-9.75-9.75 0-1.33.266-2.597.748-3.752A9.753 9.753 0 003 11.25C3 16.635 7.365 21 12.75 21a9.753 9.753 0 009.002-5.998z"
				/>
			</svg>
		</div>
	</div>
</button>

<script lang="ts">
	import ThemeToggle from '$lib/components/ThemeToggle.svelte';
	const { children } = $props();
</script>

<div
	class="flex h-screen w-screen flex-col overflow-hidden bg-white font-sans text-gray-900 transition-colors duration-500 dark:bg-gray-950 dark:text-white"
>
	<!-- Floating Theme Toggle for minimalism -->
	<div class="fixed right-6 bottom-6 z-50">
		<ThemeToggle />
	</div>

	<main class="flex flex-grow items-center justify-center">
		{@render children()}
	</main>
</div>

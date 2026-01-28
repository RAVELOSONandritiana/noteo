<script lang="ts">
	import { onMount, tick } from 'svelte';
	import { fade, slide, fly } from 'svelte/transition';

	// --- State & Types ---
	interface Note {
		id: string;
		title: string;
		content: string;
		lastModified: number;
	}

	interface Chapter {
		id: string;
		title: string;
		notes: Note[];
	}

	interface Subject {
		id: string;
		title: string;
		chapters: Chapter[];
	}

	let subjects = $state<Subject[]>([
		{
			id: '1',
			title: 'Informatique',
			chapters: [
				{
					id: '1-1',
					title: 'Algorithmes',
					notes: [
						{
							id: '1-1-1',
							title: 'Introduction',
							content:
								'<h2>Introduction aux Algorithmes</h2><p>Un algorithme est une suite finie et non ambigüe d’opérations permettant de résoudre un problème.</p>',
							lastModified: Date.now()
						}
					]
				}
			]
		}
	]);

	let activeNoteId = $state('1-1-1');
	let activeNote = $derived(
		subjects.flatMap((s) => s.chapters.flatMap((c) => c.notes)).find((n) => n.id === activeNoteId)
	);

	let aiResponse = $state('');
	let isProcessing = $state(false);
	let editorElement = $state<HTMLDivElement | null>(null);
	let showSidebar = $state(true);
	let showSymbolPicker = $state(false);

	const symbols = [
		{
			group: 'Math',
			items: ['±', '×', '÷', '≈', '≠', '≤', '≥', '∞', '√', 'π', '∑', '∫', 'Δ', 'Ω']
		},
		{ group: 'Grec', items: ['α', 'β', 'γ', 'δ', 'ε', 'ζ', 'η', 'θ', 'λ', 'μ', 'φ', 'ψ', 'ω'] },
		{ group: 'Autres', items: ['→', '⇒', '↔', '©', '®', '™', '€', '£', '¥', '§', '¶', '•', '⭐'] }
	];

	// --- Style Presets ---
	const styles = {
		title: {
			label: 'Titre',
			class: 'text-4xl font-extrabold text-blue-600 dark:text-blue-400 mb-4 block',
			color: '#2563eb'
		},
		paragraph: {
			label: 'Paragraphe',
			class: 'text-lg text-gray-700 dark:text-gray-300 leading-relaxed mb-2 block',
			color: '#374151'
		}
	};

	// --- AI Configuration ---
	const aiOptions = [
		{
			id: 'explain',
			label: 'Expliquer',
			icon: '🔍',
			prompt: 'Explique ce texte de manière détaillée mais concise :'
		},
		{
			id: 'example',
			label: 'Exemple',
			icon: '💡',
			prompt: 'Donne des exemples concrets pour ce concept :'
		},
		{ id: 'define', label: 'Définir', icon: '📖', prompt: 'Donne une définition claire pour :' },
		{
			id: 'improve',
			label: 'Améliorer',
			icon: '✨',
			prompt: 'Améliore la clarté et le style de ce texte :'
		}
	];

	// --- Methods ---
	function execCommand(command: string, value: string | undefined = undefined) {
		document.execCommand(command, false, value);
		if (activeNote && editorElement) {
			activeNote.content = editorElement.innerHTML;
		}
	}

	function insertSymbol(symbol: string) {
		execCommand('insertText', symbol);
		showSymbolPicker = false;
	}

	function applyPreset(presetKey: keyof typeof styles) {
		const style = styles[presetKey];
		if (presetKey === 'title') {
			execCommand('formatBlock', 'H2');
		} else {
			execCommand('formatBlock', 'P');
		}
		execCommand('foreColor', style.color);
	}

	async function askAI(option: (typeof aiOptions)[0]) {
		const selection = window.getSelection();
		const textToProcess = selection?.toString() || editorElement?.innerText || '';

		if (!textToProcess.trim()) return;

		isProcessing = true;
		aiResponse = '';

		try {
			// @ts-ignore
			const response = await puter.ai.chat(`${option.prompt}\n\n${textToProcess}`);
			aiResponse = response.toString();
		} catch (error) {
			console.error('Puter AI error:', error);
			aiResponse = "Erreur: Impossible de contacter l'IA.";
		} finally {
			isProcessing = false;
		}
	}

	function appendToNote(presetKey: keyof typeof styles = 'paragraph') {
		if (aiResponse && activeNote) {
			const style = styles[presetKey];
			const styledResponse =
				presetKey === 'title'
					? `<h2 style="color: ${style.color}">${aiResponse}</h2>`
					: `<p style="color: ${style.color}">${aiResponse}</p>`;

			activeNote.content += styledResponse;
			if (editorElement) editorElement.innerHTML = activeNote.content;
			aiResponse = '';
		}
	}

	function createNote(chapterId: string) {
		const subject = subjects.find((s) => s.chapters.some((c) => c.id === chapterId));
		const chapter = subject?.chapters.find((c) => c.id === chapterId);
		if (chapter) {
			const newId = `note-${Date.now()}`;
			const newNote: Note = {
				id: newId,
				title: 'Nouvelle Note',
				content: '<p>Commencez à écrire ici...</p>',
				lastModified: Date.now()
			};
			chapter.notes.push(newNote);
			activeNoteId = newId;
		}
	}

	function createSubject() {
		const newId = `subject-${Date.now()}`;
		subjects.push({
			id: newId,
			title: 'Nouvelle Matière',
			chapters: []
		});
	}

	function createChapter(subjectId: string) {
		const subject = subjects.find((s) => s.id === subjectId);
		if (subject) {
			const newId = `chapter-${Date.now()}`;
			const newChapter: Chapter = {
				id: newId,
				title: 'Nouveau Chapitre',
				notes: []
			};
			subject.chapters.push(newChapter);
		}
	}

	function deleteNote(chapterId: string, noteId: string) {
		const subject = subjects.find((s) => s.chapters.some((c) => c.id === chapterId));
		const chapter = subject?.chapters.find((c) => c.id === chapterId);
		if (chapter) {
			chapter.notes = chapter.notes.filter((n) => n.id !== noteId);
			if (activeNoteId === noteId) {
				activeNoteId = '';
			}
		}
	}

	$effect(() => {
		if (editorElement && activeNote) {
			editorElement.innerHTML = activeNote.content;
		}
	});

	function handleInput() {
		if (activeNote && editorElement) {
			activeNote.content = editorElement.innerHTML;
		}
	}
</script>

<div
	class="flex h-screen overflow-hidden bg-white text-gray-900 transition-colors duration-500 dark:bg-gray-950 dark:text-white"
>
	<!-- Sidebar: Organization -->
	{#if showSidebar}
		<aside
			transition:fly={{ x: -288, duration: 400 }}
			class="flex w-72 flex-col border-r border-gray-200 bg-gray-50 backdrop-blur-xl dark:border-gray-800 dark:bg-gray-900/50"
		>
			<div
				class="flex items-center justify-between border-b border-gray-200 p-6 dark:border-gray-800"
			>
				<h1
					class="bg-gradient-to-r from-blue-600 to-indigo-500 bg-clip-text text-xl font-black text-transparent"
				>
					Noteo
				</h1>
				<button
					onclick={createSubject}
					class="rounded-lg p-1.5 text-xs transition-colors hover:bg-gray-200 dark:hover:bg-white/10"
					title="Ajouter une Matière"
				>
					➕
				</button>
			</div>
			<nav class="custom-scrollbar flex-1 overflow-y-auto p-4">
				{#each subjects as subject}
					<div class="mb-6">
						<div
							class="group mb-3 flex items-center justify-between px-2 text-[10px] font-black tracking-widest text-gray-500 uppercase dark:text-neutral-500"
						>
							<input
								bind:value={subject.title}
								class="w-full border-none bg-transparent font-black outline-none focus:text-blue-600 dark:focus:text-blue-400"
							/>
							<button
								onclick={() => createChapter(subject.id)}
								class="rounded p-1 opacity-0 transition-all group-hover:opacity-100 hover:bg-gray-200 dark:hover:bg-white/10"
								title="Ajouter un Chapitre"
							>
								➕
							</button>
						</div>
						<div class="space-y-1">
							{#each subject.chapters as chapter}
								<div class="group">
									<div
										class="flex cursor-pointer items-center justify-between rounded-lg p-2 text-sm text-gray-600 transition-colors hover:bg-gray-200 dark:text-neutral-400 dark:hover:bg-white/5"
									>
										<div class="flex flex-1 items-center gap-2">
											<span class="text-blue-600/50 dark:text-blue-500/50">📁</span>
											<input
												bind:value={chapter.title}
												class="w-full cursor-pointer border-none bg-transparent font-medium outline-none focus:text-gray-900 dark:focus:text-white"
											/>
										</div>
										<button
											onclick={() => createNote(chapter.id)}
											class="rounded p-1 opacity-0 transition-all group-hover:opacity-100 hover:bg-gray-300 dark:hover:bg-white/10"
											title="Ajouter une Note"
										>
											➕
										</button>
									</div>
									<div
										class="mt-1 ml-4 space-y-1 border-l border-gray-200 pl-2 dark:border-white/5"
									>
										{#each chapter.notes as note}
											<div class="group/note flex items-center justify-between gap-1">
												<button
													onclick={() => (activeNoteId = note.id)}
													class="flex-1 rounded-lg p-2 text-left text-xs transition-all {activeNoteId ===
													note.id
														? 'border border-blue-600/20 bg-blue-600/10 font-bold text-blue-600 dark:text-blue-400'
														: 'text-gray-500 hover:bg-gray-200 hover:text-gray-900 dark:text-neutral-500 dark:hover:bg-white/5 dark:hover:text-neutral-300'}"
												>
													{note.title}
												</button>
												<button
													onclick={() => deleteNote(chapter.id, note.id)}
													class="group-note/hover:opacity-100 p-1 text-[10px] opacity-0 transition-opacity hover:text-red-500"
												>
													✕
												</button>
											</div>
										{/each}
									</div>
								</div>
							{/each}
						</div>
					</div>
				{/each}
			</nav>
		</aside>
	{/if}

	<!-- Main Stage -->
	<main class="relative flex flex-1 flex-col overflow-hidden">
		<!-- Toolbar -->
		<header
			class="z-10 flex h-16 items-center justify-between border-b border-gray-200 bg-white/80 px-6 backdrop-blur-md transition-colors dark:border-gray-800 dark:bg-gray-950/30"
		>
			<div class="flex items-center gap-4">
				<button
					onclick={() => (showSidebar = !showSidebar)}
					class="rounded-lg border border-gray-200 p-2 transition-colors hover:bg-gray-100 dark:border-white/5 dark:hover:bg-white/5"
				>
					{showSidebar ? '◀' : '▶'}
				</button>

				<div class="mx-2 h-6 w-px bg-gray-200 dark:bg-gray-800"></div>

				<div class="flex items-center gap-1">
					<button
						onclick={() => applyPreset('title')}
						class="rounded-md border border-gray-200 px-3 py-1.5 text-[10px] font-black tracking-widest uppercase transition-all hover:bg-gray-100 dark:border-white/5 dark:hover:bg-white/10"
						>Titre</button
					>
					<button
						onclick={() => applyPreset('paragraph')}
						class="rounded-md border border-gray-200 px-3 py-1.5 text-[10px] font-black tracking-widest uppercase transition-all hover:bg-gray-100 dark:border-white/5 dark:hover:bg-white/10"
						>Paragraphe</button
					>
				</div>

				<div class="mx-2 h-6 w-px bg-gray-200 dark:bg-gray-800"></div>

				<div class="flex items-center gap-1">
					<button
						onclick={() => execCommand('bold')}
						class="rounded-md p-2 text-sm font-bold hover:bg-gray-100 dark:hover:bg-white/10"
						>B</button
					>
					<button
						onclick={() => execCommand('italic')}
						class="rounded-md p-2 text-sm italic hover:bg-gray-100 dark:hover:bg-white/10">I</button
					>
					<div class="mx-1 h-4 w-px bg-gray-200 dark:bg-gray-800"></div>
					<button
						onclick={() => execCommand('justifyLeft')}
						class="rounded-md p-2 hover:bg-gray-100 dark:hover:bg-white/10">≡</button
					>
					<button
						onclick={() => execCommand('justifyCenter')}
						class="rounded-md p-2 hover:bg-gray-100 dark:hover:bg-white/10">≣</button
					>
					<button
						onclick={() => execCommand('justifyRight')}
						class="rounded-md p-2 text-right hover:bg-gray-100 dark:hover:bg-white/10">≡</button
					>
				</div>

				<div class="mx-2 h-6 w-px bg-gray-200 dark:bg-gray-800"></div>

				<div class="relative">
					<button
						onclick={() => (showSymbolPicker = !showSymbolPicker)}
						class="flex items-center gap-2 rounded-md border border-gray-200 px-3 py-1.5 text-[10px] font-black tracking-widest uppercase transition-all hover:bg-gray-100 dark:border-white/5 dark:hover:bg-white/10"
					>
						<span class="text-blue-600 dark:text-blue-400">Ω</span>
						<span>Symboles</span>
					</button>

					{#if showSymbolPicker}
						<div
							transition:fade={{ duration: 100 }}
							class="absolute top-full left-0 z-50 mt-2 w-64 overflow-hidden rounded-xl border border-gray-200 bg-white p-4 shadow-2xl dark:border-gray-800 dark:bg-gray-900"
						>
							<div class="space-y-4">
								{#each symbols as group}
									<div>
										<h3
											class="mb-2 px-1 text-[9px] font-black tracking-widest text-gray-400 uppercase dark:text-neutral-500"
										>
											{group.group}
										</h3>
										<div class="grid grid-cols-6 gap-1">
											{#each group.items as symbol}
												<button
													onclick={() => insertSymbol(symbol)}
													class="flex h-8 w-8 items-center justify-center rounded text-sm transition-colors hover:bg-gray-100 dark:hover:bg-white/10"
												>
													{symbol}
												</button>
											{/each}
										</div>
									</div>
								{/each}
							</div>
						</div>
					{/if}
				</div>

				<div class="mx-2 h-6 w-px bg-gray-200 dark:bg-gray-800"></div>

				<div class="flex items-center gap-2">
					<input
						type="color"
						oninput={(e) => execCommand('foreColor', (e.target as HTMLInputElement).value)}
						class="h-6 w-6 cursor-pointer overflow-hidden rounded border border-gray-200 bg-transparent dark:border-gray-800"
					/>
				</div>
			</div>

			<div class="flex items-center gap-4">
				<span
					class="text-[10px] font-bold tracking-tighter text-gray-400 uppercase italic dark:text-neutral-500"
					>Auto-sauvegardé</span
				>
				<div
					class="h-1.5 w-1.5 rounded-full bg-blue-600 shadow-[0_0_8px_rgba(37,99,235,0.4)]"
				></div>
			</div>
		</header>

		<!-- Content Area -->
		<div class="flex flex-1 overflow-hidden">
			<!-- Editor -->
			<div
				class="custom-scrollbar flex flex-1 justify-center overflow-y-auto bg-gray-50/30 p-12 dark:bg-transparent"
			>
				<div class="min-h-full w-full max-w-4xl">
					{#if activeNote}
						<input
							bind:value={activeNote.title}
							class="mb-12 w-full border-none bg-transparent text-5xl font-black text-gray-900 transition-all outline-none placeholder:text-gray-200 focus:placeholder:opacity-50 dark:text-white dark:placeholder:text-gray-800"
							placeholder="Titre de la note"
						/>
						<div
							bind:this={editorElement}
							contenteditable="true"
							oninput={handleInput}
							class="rich-editor min-h-[600px] w-full text-lg text-gray-700 outline-none selection:bg-blue-100 dark:text-neutral-300 dark:selection:bg-blue-900/40"
						></div>
					{:else}
						<div class="flex h-full flex-col items-center justify-center opacity-30 select-none">
							<span class="mb-4 text-6xl">✍️</span>
							<p class="text-sm font-black tracking-widest uppercase">Sélectionnez une note</p>
						</div>
					{/if}
				</div>
			</div>

			<!-- AI Control Panel -->
			<aside
				class="flex w-80 flex-col gap-6 overflow-y-auto border-l border-gray-200 bg-gray-50/50 p-6 backdrop-blur-md dark:border-gray-800 dark:bg-gray-900/20"
			>
				<div>
					<h2
						class="mb-4 text-[10px] font-black tracking-widest text-gray-400 uppercase dark:text-neutral-500"
					>
						Assistant Intelligent
					</h2>
					<div class="space-y-2">
						{#each aiOptions as option}
							<button
								onclick={() => askAI(option)}
								disabled={isProcessing}
								class="group flex w-full items-center gap-3 rounded-xl border border-gray-200 bg-white px-4 py-3 text-left shadow-sm transition-all hover:border-blue-600 hover:shadow-blue-600/10 disabled:opacity-50 dark:border-white/5 dark:bg-white/5 dark:hover:border-blue-400"
							>
								<span class="text-xl transition-transform group-hover:scale-110">{option.icon}</span
								>
								<span class="text-[10px] font-black tracking-widest uppercase">{option.label}</span>
							</button>
						{/each}
					</div>
				</div>

				{#if aiResponse || isProcessing}
					<div
						transition:slide
						class="flex min-h-[250px] flex-1 flex-col overflow-hidden rounded-2xl border border-blue-600/30 bg-white shadow-2xl shadow-blue-600/5 dark:border-blue-400/30 dark:bg-gray-900 dark:shadow-blue-400/5"
					>
						<div
							class="flex items-center justify-between border-b border-gray-100 bg-blue-600/5 px-4 py-2 dark:border-white/10 dark:bg-blue-400/5"
						>
							<span
								class="text-[9px] font-black tracking-widest text-blue-600 uppercase dark:text-blue-400"
								>Réponse IA</span
							>
							{#if isProcessing}
								<div class="flex gap-1">
									<div
										class="h-1 w-1 animate-bounce rounded-full bg-blue-600 dark:bg-blue-400"
									></div>
									<div
										class="h-1 w-1 animate-bounce rounded-full bg-blue-600 [animation-delay:0.2s] dark:bg-blue-400"
									></div>
									<div
										class="h-1 w-1 animate-bounce rounded-full bg-blue-600 [animation-delay:0.4s] dark:bg-blue-400"
									></div>
								</div>
							{/if}
						</div>

						<div
							class="flex-1 overflow-y-auto p-4 text-xs leading-relaxed whitespace-pre-wrap text-gray-600 italic dark:text-neutral-300"
						>
							{#if isProcessing}
								<p class="text-gray-400 dark:text-neutral-500">Noteo analyse vos données...</p>
							{:else}
								{aiResponse}
							{/if}
						</div>

						{#if !isProcessing && aiResponse}
							<div class="flex flex-col gap-2 border-t border-gray-100 p-3 dark:border-white/10">
								<button
									onclick={() => appendToNote('paragraph')}
									class="w-full rounded-lg border border-blue-600/30 bg-blue-600/10 py-2 text-[9px] font-black tracking-widest text-blue-600 uppercase transition-all hover:bg-blue-600 hover:text-white dark:bg-blue-600/20 dark:text-blue-400"
								>
									En tant que Paragraphe
								</button>
								<button
									onclick={() => appendToNote('title')}
									class="w-full rounded-lg border border-indigo-600/30 bg-indigo-600/10 py-2 text-[9px] font-black tracking-widest text-indigo-600 uppercase transition-all hover:bg-indigo-600 hover:text-white dark:bg-indigo-600/20 dark:text-indigo-400"
								>
									En tant que Titre
								</button>
							</div>
						{/if}
					</div>
				{/if}
			</aside>
		</div>
	</main>
</div>

<style>
	:global(body) {
		background-color: #ffffff;
		overflow: hidden;
		transition: background-color 0.5s ease;
	}

	:global(.dark body) {
		background-color: #030712; /* gray-950 */
	}

	.rich-editor :global(h2) {
		margin-bottom: 1.5rem;
		font-size: 1.875rem;
		line-height: 2.25rem;
		font-weight: 900;
		letter-spacing: -0.025em;
	}

	.rich-editor :global(p) {
		margin-bottom: 1.25rem;
		line-height: 1.75;
	}

	.rich-editor :global(ul) {
		margin-bottom: 1.25rem;
		margin-left: 1.5rem;
		list-style-type: disc;
	}

	.custom-scrollbar::-webkit-scrollbar {
		width: 3px;
	}

	.custom-scrollbar::-webkit-scrollbar-track {
		background: transparent;
	}

	.custom-scrollbar::-webkit-scrollbar-thumb {
		background: rgba(0, 0, 0, 0.1);
		border-radius: 10px;
	}

	:global(.dark) .custom-scrollbar::-webkit-scrollbar-thumb {
		background: rgba(255, 255, 255, 0.05);
	}

	input[type='color']::-webkit-color-swatch-wrapper {
		padding: 0;
	}
	input[type='color']::-webkit-color-swatch {
		border: none;
		border-radius: 4px;
	}
</style>

<div class="flex h-screen items-center justify-center p-6">
	<!-- Background Flourish -->
	<div class="absolute inset-0 -z-10 bg-white transition-colors duration-500 dark:bg-gray-950">
		<div
			class="absolute top-1/2 left-1/2 h-[600px] w-full -translate-x-1/2 -translate-y-1/2 bg-gradient-to-tr from-blue-50/30 to-indigo-50/30 opacity-60 blur-[120px] dark:from-blue-900/10 dark:to-indigo-900/10"
		></div>
	</div>

	<div class="w-full max-w-5xl">
		<div class="group relative">
			<div
				class="absolute -inset-1 rounded-3xl bg-gradient-to-r from-blue-600 to-indigo-600 opacity-10 blur transition-opacity group-hover:opacity-20"
			></div>
			<div
				class="relative rounded-[2rem] border border-white/20 bg-white/70 p-6 shadow-2xl backdrop-blur-xl sm:p-8 dark:border-white/10 dark:bg-gray-900/70"
			>
				<div class="mx-auto max-w-xl">
					<form action="#" method="POST" class="space-y-4">
						<div>
							<label
								for="email"
								class="mb-2 ml-1 block text-[10px] font-black tracking-widest text-gray-400 uppercase dark:text-gray-500"
								>Email Address</label
							>
							<input
								type="email"
								id="email"
								required
								class="w-full rounded-xl border border-gray-100 bg-white px-6 py-2.5 text-sm font-medium transition-all outline-none focus:border-transparent focus:ring-2 focus:ring-blue-600 dark:border-gray-800 dark:bg-gray-950"
								placeholder="you@university.edu"
							/>
						</div>
						<div>
							<div class="mb-2 ml-1 flex items-center justify-between">
								<label
									for="password"
									class="block text-[10px] font-black tracking-widest text-gray-400 uppercase dark:text-gray-500"
									>Password</label
								>
								<a
									href="#"
									class="text-[9px] font-black tracking-widest text-blue-600 uppercase hover:underline"
									>Forgot?</a
								>
							</div>
							<input
								type="password"
								id="password"
								required
								class="w-full rounded-xl border border-gray-100 bg-white px-6 py-2.5 text-sm font-medium transition-all outline-none focus:border-transparent focus:ring-2 focus:ring-blue-600 dark:border-gray-800 dark:bg-gray-950"
								placeholder="••••••••"
							/>
						</div>
						<button
							type="submit"
							class="flex w-full items-center justify-center gap-2 rounded-xl bg-gray-900 py-4 text-sm font-black text-white shadow-xl transition-all hover:scale-[1.01] active:scale-95 dark:bg-white dark:text-gray-900"
						>
							Log In
						</button>
					</form>

					<div class="mt-8 border-t border-gray-100 pt-8 text-center dark:border-gray-800">
						<p class="text-sm font-medium text-gray-500 dark:text-gray-400">
							New to Noteo?
							<a href="/auth/signup" class="ml-1 font-bold text-blue-600 hover:underline"
								>Create Account</a
							>
						</p>
					</div>
				</div>
			</div>
		</div>
	</div>
</div>

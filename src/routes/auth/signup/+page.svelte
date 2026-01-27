<div class="flex h-screen items-center justify-center p-6">
	<!-- Background Flourish -->
	<div class="absolute inset-0 -z-10 bg-white transition-colors duration-500 dark:bg-gray-950">
		<div
			class="absolute top-0 right-0 h-[500px] w-[500px] animate-pulse rounded-full bg-blue-400/5 blur-[100px] dark:bg-blue-600/5"
		></div>
		<div
			class="absolute bottom-0 left-1/4 h-[400px] w-[400px] animate-pulse rounded-full bg-indigo-400/5 dark:bg-indigo-600/5"
			style="animation-delay: 2s; filter: blur(80px);"
		></div>
	</div>

	<div class="w-full max-w-5xl">
		<div class="relative">
			<div
				class="absolute -inset-1 rounded-[2rem] bg-gradient-to-br from-blue-600 via-indigo-600 to-purple-600 opacity-5 blur transition-opacity hover:opacity-10"
			></div>
			<div
				class="relative rounded-[2.5rem] border border-white/20 bg-white/70 p-6 shadow-2xl backdrop-blur-xl sm:p-8 dark:border-white/10 dark:bg-gray-900/70"
			>
				<div class="mx-auto max-w-3xl">
					<div class="mb-6 text-center">
						<h1
							class="text-[10px] font-black tracking-[0.4em] text-gray-400 uppercase dark:text-gray-500"
						>
							Sign Up
						</h1>
					</div>
					<form action="#" method="POST" class="space-y-4">
						<div class="grid grid-cols-2 gap-6">
							<div>
								<label
									for="fname"
									class="mb-2 ml-1 block text-[10px] font-black tracking-widest text-gray-400 uppercase dark:text-gray-500"
									>First Name</label
								>
								<input
									type="text"
									id="fname"
									required
									class="w-full rounded-2xl border border-gray-100 bg-white px-6 py-2.5 text-sm font-medium transition-all outline-none focus:ring-2 focus:ring-blue-600 dark:border-gray-800 dark:bg-gray-950"
									placeholder="Jane"
								/>
							</div>
							<div>
								<label
									for="lname"
									class="mb-2 ml-1 block text-[10px] font-black tracking-widest text-gray-400 uppercase dark:text-gray-500"
									>Last Name</label
								>
								<input
									type="text"
									id="lname"
									required
									class="w-full rounded-2xl border border-gray-100 bg-white px-6 py-2.5 text-sm font-medium transition-all outline-none focus:ring-2 focus:ring-blue-600 dark:border-gray-800 dark:bg-gray-950"
									placeholder="Doe"
								/>
							</div>
						</div>
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
								class="w-full rounded-2xl border border-gray-100 bg-white px-6 py-2.5 text-sm font-medium transition-all outline-none focus:ring-2 focus:ring-blue-600 dark:border-gray-800 dark:bg-gray-950"
								placeholder="jane@example.com"
							/>
						</div>
						<div>
							<label
								for="password"
								class="mb-2 ml-1 block text-[10px] font-black tracking-widest text-gray-400 uppercase dark:text-gray-500"
								>Password</label
							>
							<input
								type="password"
								id="password"
								required
								class="w-full rounded-xl border border-gray-100 bg-white px-6 py-2.5 text-sm font-medium transition-all outline-none focus:ring-2 focus:ring-blue-600 dark:border-gray-800 dark:bg-gray-950"
								placeholder="••••••••"
							/>
						</div>

						<div class="flex items-start gap-3 py-2">
							<input
								type="checkbox"
								id="terms"
								required
								class="mt-1 h-4 w-4 rounded border-gray-300 bg-gray-50 text-blue-600 focus:ring-blue-600 dark:border-gray-700 dark:bg-gray-800"
							/>
							<label for="terms" class="text-[10px] leading-relaxed font-medium text-gray-500">
								I agree to Noteo's <a
									href="/terms-of-service"
									class="font-bold text-blue-600 hover:underline">Terms</a
								>
								and
								<a href="/privacy-policy" class="font-bold text-blue-600 hover:underline"
									>Privacy Policy</a
								>
							</label>
						</div>

						<button
							type="submit"
							class="w-full rounded-xl bg-blue-600 py-4 text-sm font-black text-white shadow-xl transition-all hover:bg-blue-700 active:scale-95"
						>
							Create Account
						</button>
					</form>

					<div class="mt-8 border-t border-gray-100 pt-8 text-center dark:border-gray-800">
						<p class="text-sm font-medium text-gray-500 dark:text-gray-400">
							Already have an account?
							<a href="/auth/login" class="ml-1 font-bold text-blue-600 hover:underline"
								>Log in here</a
							>
						</p>
					</div>
				</div>
			</div>
		</div>
	</div>
</div>

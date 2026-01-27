<div class="flex min-h-screen items-center justify-center px-4 py-12 sm:px-6 lg:px-8">
	<div
		class="w-full max-w-md space-y-8 rounded-3xl border border-gray-100 bg-white p-10 shadow-xl dark:border-gray-800 dark:bg-gray-950"
	>
		<div>
			<div
				class="mx-auto flex h-12 w-12 items-center justify-center rounded-xl bg-blue-600 text-xl font-bold text-white"
			>
				N
			</div>
			<h2 class="mt-6 text-center text-3xl font-black tracking-tight text-gray-900 dark:text-white">
				Create your account
			</h2>
			<p class="mt-2 text-center text-sm text-gray-600 dark:text-gray-400">
				Already have an account? <a
					href="/login"
					class="font-medium text-blue-600 hover:text-blue-500">Sign in</a
				>
			</p>
		</div>
		<form class="mt-8 space-y-6">
			<div class="space-y-4 rounded-md shadow-sm">
				<div>
					<label for="full-name" class="sr-only">Full Name</label>
					<input
						id="full-name"
						name="name"
						type="text"
						required
						class="relative block w-full rounded-xl border-0 px-4 py-3 text-gray-900 ring-1 ring-gray-300 ring-inset placeholder:text-gray-400 focus:z-10 focus:ring-2 focus:ring-blue-600 focus:ring-inset sm:text-sm sm:leading-6 dark:bg-gray-900 dark:text-white dark:ring-gray-700"
						placeholder="Full Name"
					/>
				</div>
				<div>
					<label for="email" class="sr-only">Email address</label>
					<input
						id="email"
						name="email"
						type="email"
						required
						class="relative block w-full rounded-xl border-0 px-4 py-3 text-gray-900 ring-1 ring-gray-300 ring-inset placeholder:text-gray-400 focus:z-10 focus:ring-2 focus:ring-blue-600 focus:ring-inset sm:text-sm sm:leading-6 dark:bg-gray-900 dark:text-white dark:ring-gray-700"
						placeholder="Email address"
					/>
				</div>
				<div>
					<label for="password" class="sr-only">Password</label>
					<input
						id="password"
						name="password"
						type="password"
						required
						class="relative block w-full rounded-xl border-0 px-4 py-3 text-gray-900 ring-1 ring-gray-300 ring-inset placeholder:text-gray-400 focus:z-10 focus:ring-2 focus:ring-blue-600 focus:ring-inset sm:text-sm sm:leading-6 dark:bg-gray-900 dark:text-white dark:ring-gray-700"
						placeholder="Password"
					/>
				</div>
			</div>

			<div class="text-xs text-gray-500">
				By signing up, you agree to our <a href="/terms-of-service" class="text-blue-600 underline"
					>Terms</a
				>
				and <a href="/privacy-policy" class="text-blue-600 underline">Privacy Policy</a>.
			</div>

			<button
				type="submit"
				class="group relative flex w-full justify-center rounded-xl bg-blue-600 px-4 py-3 text-sm font-bold text-white transition-all hover:bg-blue-700 focus:ring-2 focus:ring-blue-500 focus:ring-offset-2 focus:outline-none"
			>
				Create account
			</button>
		</form>
	</div>
</div>

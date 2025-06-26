<script>
	import Contact from '$lib/+Contact.svelte';
</script>

<div class="mt-25 px-4 sm:px-6 lg:px-10 xl:px-11">
	<nav class="rounded-2xl px-4 py-3">
		<div class="flex flex-wrap items-center justify-start lg:justify-end">
			<!-- Right Section (Buttons) -->
			 <div class="px-5 bg-[#0D0B0F] border border-white/5 rounded-2xl py-3 font-inter-tight">
			<div
				class="flex w-full flex-wrap items-center justify-start gap-2  sm:w-auto sm:justify-end"
			>
				<a href="/get-started" class="mb-2 sm:mb-0">
					<button
						class="font-inter-tight flex h-9 items-center rounded-md border border-white/5 px-3 py-2 text-sm font-medium text-white transition-colors hover:bg-white/5"
					>
						Home
					</button>
				</a>

				<a href="/Subscription">
					<button
						class="font-inter-tight flex h-9 items-center rounded-md border border-white/5 px-3 py-2 text-[14px] font-medium leading-5 tracking-normal transition-colors hover:bg-white/5"
					>
						<!-- <img src={Star} alt="Alert Icon" class="mr-2 h-4 w-4" /> -->
						<span
							class="font-inter-tight h-[20px] w-[85px] text-[13px] font-medium leading-5 tracking-normal"
							>Leaderboard</span
						>
					</button>
				</a>
				<a href="/Subscription">
					<button
						class="font-inter-tight flex h-9 items-center rounded-md border border-white/5 px-3 py-2 text-[14px] font-medium leading-5 tracking-normal transition-colors hover:bg-white/5"
					>
						<!-- <img src={Star} alt="Alert Icon" class="mr-2 h-4 w-4" /> -->
						<span
							class="font-inter-tight h-[20px] text-[13px] font-medium leading-5 tracking-normal"
							>Friends</span
						>
					</button>
				</a>

				<a href="/Subscription">
					<button
						class="font-inter-tight flex h-9 items-center rounded-md border border-white/5 px-3 py-2 text-[14px] font-medium leading-5 tracking-normal transition-colors hover:bg-white/5"
					>
						<!-- <img src={Star} alt="Alert Icon" class="mr-2 h-4 w-4" /> -->
						<span
							class="font-inter-tight h-[20px] text-[13px] font-medium leading-5 tracking-normal"
							>Clinet</span
						>
					</button>
				</a>

				<a href="/Subscription">
					<button
						class="font-inter-tight flex h-9 items-center rounded-md border border-white/5 px-3 py-2 text-[14px] font-medium leading-5 tracking-normal transition-colors hover:bg-white/5"
					>
						<!-- <img src={Star} alt="Alert Icon" class="mr-2 h-4 w-4" /> -->
						<span
							class="font-inter-tight h-[20px] w-[85px] text-[13px] font-medium leading-5 tracking-normal"
							>Edit Profiles</span
						>
					</button>
				</a>
				<a href="/Subscription">
					<button
						class="font-inter-tight flex h-9 items-center rounded-md border border-white/5 px-3 py-2 text-[14px] font-medium leading-5 tracking-normal transition-colors hover:bg-white/5"
					>
						<!-- <img src={Star} alt="Alert Icon" class="mr-2 h-4 w-4" /> -->
						<span
							class="font-inter-tight h-[20px] w-[85px] text-[13px] font-medium leading-5 tracking-normal"
							>Subscription</span
						>
					</button>
				</a>
				<a href="/Subscription">
					<button
						class="font-inter-tight flex h-9 items-center rounded-md border border-white/5 px-3 py-2 text-[14px] font-medium leading-5 tracking-normal transition-colors hover:bg-white/5"
					>
						<!-- <img src={Star} alt="Alert Icon" class="mr-2 h-4 w-4" /> -->
						<span
							class="font-inter-tight h-[20px] w-[85px] text-[13px] font-medium leading-5 tracking-normal"
							>Transactions</span
						>
					</button>
				</a>

				<a href="/Billing">
					<button
						class="font-inter-tight flex h-9  items-center rounded-md border border-white/5 px-3 py-2 text-[14px] font-medium leading-5 tracking-normal transition-colors hover:bg-white/10"
						style="background: #252327;"
					>
						<!-- <img src={Data} alt="Alert Icon" class="mr-2 h-4 w-4" /> -->
						<span
							class="font-inter-tight h-[20px]  text-[14px] font-medium leading-5 tracking-normal"
							>Billing</span
						>
					</button>
				</a>
			</div>
		</div>
		</div>
	</nav>
</div>

<div class="mx-4 my-10 sm:mx-6 md:mx-10">
	<p class="text-[39px] font-bold font-inter-tight">Billing</p>
</div>

<div class="mx-4 flex justify-center sm:mx-6 md:mx-10">
	<div class="flex w-full flex-col rounded-2xl border border-white/5 bg-[#0D0B0F] p-4">
		<!-- Heading -->
		<div class="py-3">
			<span class="text-base text-white text-[18px] sm:text-lg">Your Subscription</span>
		</div>

		<!-- Tier -->
		<div class="py-3 text-xl font-bold italic text-white sm:text-2xl">
			<span>TIER 3</span>
		</div>

		<!-- Badge -->
		<div class="flex flex-wrap items-center gap-3 py-3">
			<img
				class="h-10 w-9 drop-shadow-[0_0_20px_rgba(221,3,85,0.7)]"
				src="/Tier4.png"
				alt="Tier Badge"
			/>
			<span class="text-xl font-extrabold text-white sm:text-2xl lg:text-4xl">UNDERGROUND</span>
		</div>

		<!-- Renewal & Actions -->
		<div
			class="flex flex-col items-start justify-between gap-4 py-3 text-sm text-white sm:flex-row sm:items-center sm:text-base"
		>
			<span class="whitespace-nowrap">
				New subscription renewal: <span class="font-bold font-inter-tight  ">28.03.2024</span>
			</span>

			<div class="flex gap-[16px] font-inter-tight justify-end">
				<button class="text-purple-500 transition hover:underline ">Upgrade</button>
				<button class="transition hover:underline">Cancel</button>
			</div>
		</div>
	</div>
</div>

<script>
	import Contact from '$lib/+Contact.svelte';
</script>



<div class="mt-25  w-full px-4 sm:px-6 lg:px-10">
	<nav class="rounded-2xl border border-white/5 bg-[#0D0B0F] px-4 py-3">
		<div class="flex flex-wrap items-center justify-between">
			<!-- Left Section (Logo or Home Button if needed) -->
			<a href="/get-started" class="mb-2 sm:mb-0">
				<!-- <button
					class="font-inter-tight flex h-9 items-center rounded-md border border-white/5 px-3 py-2 text-sm font-medium text-white transition-colors hover:bg-white/5"
				>
					
				</button> -->
			</a>

			<!-- Right Section (Buttons) -->
			<div class="flex w-full flex-wrap items-center justify-start gap-2 sm:w-auto sm:justify-end">
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
							class="font-inter-tight h-[20px]  text-[13px] font-medium leading-5 tracking-normal"
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
							class="font-inter-tight h-[20px]  text-[13px] font-medium leading-5 tracking-normal"
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
						class="font-inter-tight flex h-9 w-[96px] items-center rounded-md border border-white/5 px-3 py-2 text-[14px] font-medium leading-5 tracking-normal transition-colors hover:bg-white/10"
						style="background: #252327;"
					>
						<!-- <img src={Data} alt="Alert Icon" class="mr-2 h-4 w-4" /> -->
						<span
							class="font-inter-tight h-[20px] w-[48px] text-[14px] font-medium leading-5 tracking-normal"
							>Billing</span
						>
					</button>
				</a>
			</div>
		</div>
	</nav>
</div>

<div class="mx-4 sm:mx-6 md:mx-10 my-10">
	<p class="text-6xl font-bold">Billing</p>
</div>



<div class="mx-4 sm:mx-6 md:mx-10 flex justify-center">
  <div class="flex w-full  flex-col rounded-2xl border border-white/5 bg-[#0D0B0F] p-4">
    
    <!-- Heading -->
    <div class="py-1">
      <span class="text-base sm:text-lg text-white">Your Subscription</span>
    </div>

    <!-- Tier -->
    <div class="py-1 text-xl sm:text-2xl font-bold italic text-white">
      <span>Tier 3</span>
    </div>

    <!-- Badge -->
    <div class="flex flex-wrap items-center gap-3 py-1">
      <img class="h-8 w-8 drop-shadow-[0_0_20px_rgba(221,3,85,0.7)]" src="/Tier4.png" alt="Tier Badge" />
      <span class="text-xl sm:text-2xl lg:text-4xl font-extrabold text-white">UNDERGROUND</span>
    </div>

    <!-- Renewal & Actions -->
    <div class="flex flex-col sm:flex-row justify-between items-start sm:items-center gap-4 py-2 text-white text-sm sm:text-base">
      <span>
        New subscription renewal: <span class="font-bold">28.03.2024</span>
      </span>

      <div class="flex gap-4">
        <button class="text-purple-500 hover:underline transition">Upgrade</button>
        <button class="hover:underline transition">Cancel</button>
      </div>
    </div>
  </div>
</div>




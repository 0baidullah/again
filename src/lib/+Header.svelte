<script>
	//   import { page } from '$app/stores';
	import { fade, slide } from 'svelte/transition';
	import logo from '../lib/assets/NO HESI.svg';
	import logo2 from '../lib/assets/Vector.png';
	import Alert from '../lib/assets/Ellipse 1.png';
	import Star from '../lib/assets/Star.svg';
	import Data from '../lib/assets/Database.png';
	import File from '../lib/assets/FileArrowDown.svg';
	import Bell from '../lib/assets/Bell.png';
	import Avatar from '../lib/assets/9fbd4972fc0c3ffddfc14a8b901a6aa53a99193c.jpg';
	import Arrow from '../lib/assets/Arrow.png';

	let isOpen = false;
	let isMobileMenuOpen = false;

	const toggleMobileMenu = () => {
		isMobileMenuOpen = !isMobileMenuOpen;
	};

	const closeMobileMenu = () => {
		isMobileMenuOpen = false;
	};
</script>

<div class="  flex justify-center">
	<nav
		class="fixed top-5 z-20 flex h-[60px] w-[95%] items-center justify-between rounded-2xl border border-white/5 bg-[rgba(8,6,10,0.83)] px-2 py-3"
	>
		<div class="flex items-center justify-between">
			<!-- Logo Section - Exactly as original -->
			<div
				class="xl:w-42 h-11 w-32 gap-1 rounded-xl border border-white/5"
				style="background:rgba(255, 255, 255, 0.05) ;"
			>
				<a href="/" class="flex items-center rounded px-4 py-2 text-white">
					<img src={logo2} alt="Logo" class="top-2 mr-2 h-4 w-4" />
					<img src={logo} alt="Logo" class="left-6 top-2 h-7 w-20" />
				</a>
			</div>

			<!-- Desktop Navigation Links - Show on XL and above (1280px+) -->
			<div class="hidden h-9 w-full items-center gap-2 xl:flex">
				<a href="/get-started">
					<button
						class="font-inter-tight h-[36px] w-[90px] gap-1 rounded-md p-2 text-[14px] font-medium leading-5 tracking-normal transition-colors hover:bg-white/5"
					>
						Get started
					</button>
				</a>
				<a href="/get-started">
					<button
						class="h-[36px] w-[49px] gap-1 rounded-md p-2 text-[14px] font-medium leading-5 tracking-normal transition-colors hover:bg-white/5"
					>
						Shop
					</button>
				</a>
				<a href="/get-started">
					<button
						class="h-[36px] w-[72px] gap-1 rounded-md p-2 text-[14px] font-medium leading-5 tracking-normal transition-colors hover:bg-white/5"
					>
						About us
					</button>
				</a>
				<a href="/get-started">
					<button
						class="h-[36px] w-[52px] gap-1 rounded-md p-2 text-[14px] font-medium leading-5 tracking-normal transition-colors hover:bg-white/5"
					>
						News
					</button>
				</a>
				<a href="/get-started">
					<button
						class="h-[36px] w-[73px] gap-1 rounded-md p-2 text-[14px] font-medium leading-5 tracking-normal transition-colors hover:bg-white/5"
					>
						Contacts
					</button>
				</a>
				<a href="/get-started">
					<button
						class="h-[36px] w-[42px] gap-1 rounded-md p-2 text-[14px] font-medium leading-5 tracking-normal transition-colors hover:bg-white/5"
					>
						FAQs
					</button>
				</a>
			</div>
		</div>

		<div class="flex items-center">
			<!-- Desktop Action Buttons - Show on XL and above -->
			<div class="hidden h-9 items-center gap-1 xl:flex">
				<a href="/get-started">
					<button
						class="font-inter-tight flex h-9 w-[73px] items-center rounded-md border border-white/5 px-3 py-2 text-[14px] font-medium leading-5 tracking-normal transition-colors hover:bg-white/5"
					>
						<img src={Alert} alt="Alert Icon" class="mr-2 h-4 w-4" />
						<span
							class="font-inter-tight h-[20px] w-[25px] text-[13px] font-medium leading-5 tracking-normal"
							>Live</span
						>
					</button>
				</a>

				<a href="/Subscription">
					<button
						class="font-inter-tight flex h-9 w-[133px] items-center rounded-md border border-white/5 px-3 py-2 text-[14px] font-medium leading-5 tracking-normal transition-colors hover:bg-white/5"
					>
						<img src={Star} alt="Alert Icon" class="mr-2 h-4 w-4" />
						<span
							class="font-inter-tight h-[20px] w-[85px] text-[13px] font-medium leading-5 tracking-normal"
							>Subscription</span
						>
					</button>
				</a>

				<a href="/Servers">
					<button
						class="font-inter-tight flex h-9 w-[96px] items-center rounded-md border border-white/5 px-3 py-2 text-[14px] font-medium leading-5 tracking-normal transition-colors hover:bg-white/10"
						style="background: #252327;"
					>
						<img src={Data} alt="Alert Icon" class="mr-2 h-4 w-4" />
						<span
							class="font-inter-tight h-[20px] w-[48px] text-[14px] font-medium leading-5 tracking-normal"
							>Servers</span
						>
					</button>
				</a>

				<a href="/Billing">
					<button
						class="font-inter-tight flex h-9 w-[167px] items-center rounded-md border border-white/5 px-3 py-2 text-[14px] font-medium leading-5 tracking-normal transition-colors hover:bg-white/5"
					>
						<img src={File} alt="Alert Icon" class="mr-2 h-4 w-4" />
						<span
							class="font-inter-tight h-5 w-[120px] text-[13px] font-medium leading-5 tracking-normal"
							>Download launcher</span
						>
					</button>
				</a>

				<a href="/get-started">
					<button
						class="font-inter-tight flex h-9 w-[36px] items-center rounded-md border border-white/5 px-2 py-2 text-[14px] font-medium leading-5 tracking-normal transition-colors hover:bg-white/5"
					>
						<img src={Bell} alt="Alert Icon" class="h-4 w-4" />
					</button>
				</a>

				<div
					class="ml-1 flex h-[36px] w-full items-center gap-[6px] rounded-md bg-purple-800 px-3 py-2"
				>
					<img
						src={Avatar}
						alt="User Avatar"
						class="h-[28px] w-[28px] rounded-full border border-white/5"
					/>
					<span
						class="font-inter-tight hidden h-[20px] w-[80px] text-[14px] font-medium leading-5 tracking-normal text-white xl:inline"
						>JohnDoe_911</span
					>
					<img src={Arrow} alt="Logo" class="ml-1 hidden h-[6px] w-[12px] xl:inline" />
				</div>
			</div>

			<button
				class="relative z-[60] flex h-10 w-10 items-center justify-center rounded-md border border-white/5 transition-colors hover:bg-white/5 xl:hidden"
				on:click={toggleMobileMenu}
				aria-label="Toggle menu"
			>
				{#if !isMobileMenuOpen}
					<svg class="h-6 w-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M4 6h16M4 12h16M4 18h16"
						></path>
					</svg>
				{:else}
					<svg class="h-6 w-6 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M6 18L18 6M6 6l12 12"
						></path>
					</svg>
				{/if}
			</button>
		</div>
	</nav>

	{#if isMobileMenuOpen}
		<!-- svelte-ignore a11y_click_events_have_key_events -->
		<!-- svelte-ignore a11y_no_static_element_interactions -->
		<div
			class="fixed inset-0 z-40 bg-black/60 backdrop-blur-sm xl:hidden"
			on:click={closeMobileMenu}
			transition:fade={{ duration: 250 }}
		></div>

		<div
			class="fixed left-4 right-4 top-[40px] z-50 max-h-[calc(100vh-100px)] overflow-y-auto sm:left-6 sm:right-6 md:left-8 md:right-8 xl:hidden"
			transition:slide={{ duration: 300 }}
		>
			<div
				class="rounded-2xl border border-white/10 bg-[rgba(8,6,10,0.83)] p-1 shadow-2xl backdrop-blur-xl sm:p-6"
			>
				<div class="mb-1 flex justify-end xl:hidden">
					<button
						on:click={closeMobileMenu}
						class="flex h-8 w-8 items-center justify-center rounded-full border border-white/20 transition-colors hover:bg-white/10"
						aria-label="Close menu"
					>
						<svg class=" w-5 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								stroke-width="2"
								d="M6 18L18 6M6 6l12 12"
							></path>
						</svg>
					</button>
				</div>

				<div class="">
					<div class="space-y-1">
						<a href="/get-started" on:click={closeMobileMenu} class="block">
							<div
								class="w-full rounded-lg px-4 text-left text-white transition-all duration-200 hover:bg-white/10"
							>
								<span class="text-[16px] font-medium">Get started</span>
							</div>
						</a>
						<a href="/shop" on:click={closeMobileMenu} class="block">
							<div
								class="w-full rounded-lg px-4 text-left text-white transition-all duration-200 hover:bg-white/10"
							>
								<span class="text-[16px] font-medium">Shop</span>
							</div>
						</a>
						<a href="/about" on:click={closeMobileMenu} class="block">
							<div
								class="w-full rounded-lg px-4 text-left text-white transition-all duration-200 hover:bg-white/10"
							>
								<span class="text-[16px] font-medium">About us</span>
							</div>
						</a>
						<a href="/news" on:click={closeMobileMenu} class="block">
							<div
								class="w-full rounded-lg px-4 text-left text-white transition-all duration-200 hover:bg-white/10"
							>
								<span class="text-[16px] font-medium">News</span>
							</div>
						</a>
						<a href="/contacts" on:click={closeMobileMenu} class="block">
							<div
								class="w-full rounded-lg px-4 text-left text-white transition-all duration-200 hover:bg-white/10"
							>
								<span class="text-[16px] font-medium">Contacts</span>
							</div>
						</a>
						<a href="/faqs" on:click={closeMobileMenu} class="block">
							<div
								class="w-full rounded-lg px-4 text-left text-white transition-all duration-200 hover:bg-white/10"
							>
								<span class="text-[16px] font-medium">FAQs</span>
							</div>
						</a>
					</div>
				</div>

				<div class="">
					<div class="">
						<a href="/subscription" on:click={closeMobileMenu} class="block">
							<div
								class="flex w-full items-center rounded-lg border-b border-white/5 px-4 py-2 text-white transition-all duration-200 hover:bg-white/10"
							>
								<img src={Star} alt="Subscription" class="mr-4 w-5" />
								<span class="text-[16px] font-medium">Subscription</span>
							</div>
						</a>
						<a href="/servers" on:click={closeMobileMenu} class="block">
							<div
								class="flex w-full items-center rounded-lg border-b border-white/5 bg-[#252327] px-4 py-2 text-white transition-all duration-200 hover:bg-white/15"
							>
								<img src={Data} alt="Servers" class="mr-4 w-5" />
								<span class="text-[16px] font-medium">Servers</span>
							</div>
						</a>
						<a href="/download" on:click={closeMobileMenu} class="block">
							<div
								class="flex w-full items-center rounded-lg border-b border-white/5 px-4 py-2 text-white transition-all duration-200 hover:bg-white/10"
							>
								<img src={File} alt="Download" class="mr-4 w-5" />
								<span class="text-[16px] font-medium">Download launcher</span>
							</div>
						</a>
					</div>
				</div>
			</div>
		</div>
	{/if}
</div>

<style>
	/* Smooth transitions */
	button {
		transition: background-color 0.3s ease;
	}

	/* Ensure proper text color */
	button,
	a {
		color: white;
	}

	/* Mobile menu styling */
	.space-y-1 > :not([hidden]) ~ :not([hidden]) {
		margin-top: 0.25rem;
	}

	/* Custom scrollbar */
	.overflow-y-auto::-webkit-scrollbar {
		width: 6px;
	}

	.overflow-y-auto::-webkit-scrollbar-track {
		background: rgba(255, 255, 255, 0.1);
		border-radius: 3px;
	}

	.overflow-y-auto::-webkit-scrollbar-thumb {
		background: rgba(255, 255, 255, 0.3);
		border-radius: 3px;
	}

	.overflow-y-auto::-webkit-scrollbar-thumb:hover {
		background: rgba(255, 255, 255, 0.5);
	}

	/* Ensure mobile menu button is always visible */
	.z-\[60\] {
		z-index: 60;
	}
</style>

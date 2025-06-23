<script>
	export let icon;
	export let tier;
	export let title;
	// export let price;
	// export let  anuallayprice;
	export let buttonText;
	export let giftIcon;
	export let bg;
	export let dp;
	export let btn;
	export let selectedPrice;
	export let selectedType;
	// export let month;
	import { slide, fly } from 'svelte/transition';
	import { cubicIn, cubicOut, cubicInOut } from 'svelte/easing';
	import Tick from '../lib/assets/fi_1008958.png';

	let priceChars = selectedPrice.split('');

	/**
	 * @type {any[]}
	 */
	export let features = [];
	console.log(dp);
</script>

<div
	class="flex h-[639px] flex-col items-start gap-2 rounded-lg border
          border-[rgba(255,255,255,0.1)] p-5
          pb-6 backdrop-blur-[200px]
          sm:h-[636px] sm:gap-6 sm:p-5 {bg}"
>
	{#if selectedType === 'annualy' && selectedPrice !== 'Free'}
		<div
			class="font-inter absolute right-4 top-4 w-[54px] rounded-full bg-[#6aff67] px-1 py-1 text-center text-[10px] font-bold text-black"
			in:fly={{ x: -10, opacity: 0, duration: 400, easing: cubicIn }}
			out:fly={{ x: -24, duration: 800, easing: cubicInOut }}
		>
			20%
		</div>
	{/if}

	<div class="relative flex h-[20px] w-[294px] items-center gap-2 {dp}">
		<img src={icon} alt="{tier} icon" class=" h-5 w-5 bg-none" />
		<span
			class="font-roboto flex-1 text-[16px] font-bold uppercase italic leading-[20px] tracking-[.15em] text-[rgba(238,237,238,0.87)]"
		>
			{tier}
		</span>
	</div>

	<div class="flex h-[76px] w-[294px] flex-col items-start gap-1">
		<span class="font-inter text-[20px] font-semibold leading-[24px] text-[rgba(238,237,238,0.87)]">
			{title}
		</span>

		<div class="h6-inter text-content-secondary svelte-1l3vz5j flex font-medium">
			<div
				class="inline-flex h-12 flex-col items-start justify-start overflow-hidden text-[#FAFAFA]"
			>
				<div
					class=" transition-transform duration-500 ease-in"
					style=" width:transition: transform 300ms, width :400ms cubic-bezier(0.42, 0, 0.58, 1);"
					class:roll-up={selectedType === 'annualy'}
					class:roll-down={selectedType === 'month'}
				>
					<div class="title-gradient font-inter text-4xl font-semibold leading-[48px]">
						{selectedPrice}
					</div>
					<div
						class="title-gradient font-inter justify-start text-4xl font-semibold leading-[48px]"
					>
						3.33
					</div>
					<div
						class="title-gradient font-inter justify-start text-4xl font-semibold leading-[48px]"
					>
						2.96
					</div>
					<div
						class="title-gradient font-inter justify-start text-4xl font-semibold leading-[48px]"
					>
						{selectedPrice}
					</div>
				</div>
			</div>
			<span class="font-inter flex items-end">
				{#if selectedPrice === '$12.99'}
					<span
						in:fly={{ x:5, duration: 800, easing: cubicIn }}
						out:fly={{ x: -16, duration: 800, easing: cubicInOut }}
					>
						/month
					</span>
				{:else}
					<span>/month</span>
				{/if}
			</span>
		</div>
	</div>

	<div class="flex w-full flex-col items-center gap-2">
		<div
			class="flex h-[52px] w-full items-center justify-center gap-[20px] rounded-md {btn} p-[16px_28px]"
		>
			<button class="font-roboto text-[16px] font-bold uppercase italic leading-[20px]">
				{buttonText}
			</button>
		</div>

		<div class="flex h-[25px] w-[114px] flex-none items-center gap-1">
			<img src={giftIcon} alt="gift icon" class="h-5 w-5" />
			<button
				class="font-inter flex-none text-[15px] font-medium leading-[25px] text-[rgba(255,255,255,0.48)] underline hover:text-white"
			>
				Send as a Gift
			</button>
		</div>
	</div>

	<div class="flex w-[294px] flex-col items-start gap-3">
		{#each features as feat}
			<div class="flex h-[49px] w-full items-center gap-3">
				<img src={Tick} alt="feature icon" class="h-5 w-5" />
				<span class="font-inter flex-1 text-[15px] font-medium leading-[25px] text-white">
					{feat}
				</span>
			</div>
		{/each}
	</div>
</div>

<style>
	@keyframes rollUp {
		0% {
			transform: translateY(0);
		}
		100% {
			transform: translateY(-140px);
		} /* 48px * 4 */
	}

	@keyframes rollDown {
		0% {
			transform: translateY(-140px);
		}
		100% {
			transform: translateY(0);
		}
	}

	.roll-up {
		animation: rollUp 0.2s ease-in forwards;
	}

	.roll-down {
		animation: rollDown 0.2s ease-in forwards;
	}

	.badge {
		background: #6aff67;
		color: black;
		font-size: 10px;
		left: 250px;
		font-weight: 500;
		padding-left: 5px;
		padding-right: 5px;

		@media (max-width: 320px) {
			width: 50px;
			height: 16px;
			font-size: 9px;
		}
	}
</style>

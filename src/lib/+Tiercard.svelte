<script>
	export let icon;
	export let tier;
	export let title;
	// export let price;
	// export let  anuallayprice;
	export let buttonText;

	export let bg;
	export let dp;
	export let btn;
	export let selectedPrice;
	export let selectedType;
	export let discount;
	export let month;
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

<div class="relative">
	{#if tier === 'Tier 3'}
		<div
			class="font-roboto text-md absolute left-0 top-[-34px] z-10 h-[50px] w-[100%] rounded-t-lg bg-[#dd0355] pl-5 pt-[6px] font-bold text-white"
		>
			MOST POPULAR
		</div>
	{/if}
	<div
		class="relative z-10 flex h-[639px] flex-col items-start gap-2 rounded-2xl
          border border-[rgba(255,255,255,0.1)]
          p-5 pb-6
           sm:h-[636px] sm:gap-6 sm:p-5 {bg}  backdrop-blur-2xl"
	>
		<!-- {#if tier === 'Tier 3'}
			<div
				class="font-roboto text-md absolute left-0 top-[-34px] h-[50px] w-[100%] rounded-t-lg bg-[#dd0355] pl-5 pt-[6px] font-bold text-white"
			>
				MOST POPULAR
			</div>
		{/if} -->

		{#if selectedType === 'annualy' && selectedPrice !== 'Free'}
			<div
				class="font-inter absolute right-4 top-4 w-[54px] rounded-full bg-[#6aff67] px-1 py-1 text-center text-[15px] font-bold text-black"
				in:fly={{ x: -10, opacity: 0, duration: 400, easing: cubicIn }}
				out:fly={{ x: -24, duration: 800, easing: cubicInOut }}
			>
				{discount}
			</div>
		{/if}

		<div class="relative z-40 flex h-[20px] w-[294px] items-center gap-2 {dp}">
			<img src={icon} alt="{tier} icon" class=" h-5 w-5 bg-transparent {dp} " />
			<!-- <svg class=""><use href='/Tier3.png'></use> </svg> -->
			<span
				class="font-roboto flex-1 text-[16px] font-bold uppercase italic leading-[20px] tracking-[.15em] text-[rgba(238,237,238,0.87)]"
			>
				{tier}
			</span>
		</div>

		<div class="flex h-[76px] w-[294px] flex-col items-start gap-1">
			<span
				class="font-inter text-[20px] font-semibold leading-[24px] text-[rgba(238,237,238,0.87)]"
			>
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
							in:fly={{ x: 5, duration: 800, easing: cubicIn }}
							out:fly={{ x: -16, duration: 800, easing: cubicInOut }}
						>
							{month}
						</span>
					{:else}
						<span>{month}</span>
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

			<div
				class="font-inter text-content-tertiary flex cursor-pointer items-center justify-center gap-2 fill-[#898385] text-[15px] text-[rgba(255,255,255,0.48)] underline hover:fill-[#FAFAFA] hover:text-[#FAFAFA]"
			>
				<svg class="" xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 16 16"
					><path
						d="M13.5 4.75003H11.8787C12.1107 4.41259 12.2397 4.01502 12.25 3.60566C12.2593 3.2938 12.2046 2.98335 12.0895 2.69336C11.9744 2.40338 11.8013 2.13999 11.5806 1.91938C11.36 1.69877 11.0966 1.52559 10.8067 1.41049C10.5167 1.29538 10.2062 1.24078 9.89437 1.25003C9.60633 1.25618 9.32267 1.32181 9.06121 1.44281C8.79974 1.56381 8.56612 1.73756 8.375 1.95316C8.23404 2.11395 8.10849 2.28763 8 2.47191C7.89151 2.28763 7.76596 2.11395 7.625 1.95316C7.43388 1.73756 7.20026 1.56381 6.93879 1.44281C6.67733 1.32181 6.39367 1.25618 6.10563 1.25003C5.79377 1.24078 5.48332 1.29538 5.19333 1.41049C4.90335 1.52559 4.63996 1.69877 4.41935 1.91938C4.19874 2.13999 4.02556 2.40338 3.91046 2.69336C3.79535 2.98335 3.74075 3.2938 3.75 3.60566C3.76029 4.01502 3.88926 4.41259 4.12125 4.75003H2.5C2.16848 4.75003 1.85054 4.88173 1.61612 5.11615C1.3817 5.35057 1.25 5.66851 1.25 6.00003V8.00003C1.24994 8.28819 1.34945 8.56753 1.53167 8.79076C1.7139 9.01399 1.96766 9.1674 2.25 9.22503V13C2.25 13.3316 2.3817 13.6495 2.61612 13.8839C2.85054 14.1183 3.16848 14.25 3.5 14.25H12.5C12.8315 14.25 13.1495 14.1183 13.3839 13.8839C13.6183 13.6495 13.75 13.3316 13.75 13V9.22503C14.0323 9.1674 14.2861 9.01399 14.4683 8.79076C14.6506 8.56753 14.7501 8.28819 14.75 8.00003V6.00003C14.75 5.66851 14.6183 5.35057 14.3839 5.11615C14.1495 4.88173 13.8315 4.75003 13.5 4.75003ZM13.25 7.75003H8.75V6.25003H13.25V7.75003ZM9.5 2.94816C9.55532 2.88675 9.62275 2.83745 9.69804 2.80336C9.77333 2.76926 9.85486 2.75111 9.9375 2.75003H9.95938C10.0651 2.74973 10.1699 2.77071 10.2674 2.81171C10.3649 2.85271 10.4531 2.91291 10.5269 2.98871C10.6007 3.06451 10.6584 3.15437 10.6967 3.25295C10.7351 3.35153 10.7532 3.45681 10.75 3.56253C10.7489 3.64517 10.7308 3.7267 10.6967 3.80199C10.6626 3.87728 10.6133 3.94471 10.5519 4.00003C10.1206 4.38253 9.41125 4.57878 8.825 4.67253C8.91875 4.08878 9.115 3.37941 9.5 2.94816ZM5.48125 2.98128C5.62961 2.83451 5.82944 2.75153 6.03813 2.75003H6.0625C6.14514 2.75111 6.22667 2.76926 6.30196 2.80336C6.37725 2.83745 6.44468 2.88675 6.5 2.94816C6.8825 3.37941 7.07875 4.08816 7.17188 4.67378C6.59062 4.57941 5.875 4.38316 5.44812 4.00003C5.38672 3.94471 5.33742 3.87728 5.30333 3.80199C5.26923 3.7267 5.25108 3.64517 5.25 3.56253C5.24724 3.45504 5.2663 3.34811 5.30605 3.2482C5.3458 3.1483 5.4054 3.05749 5.48125 2.98128ZM2.75 6.25003H7.25V7.75003H2.75V6.25003ZM3.75 9.25003H7.25V12.75H3.75V9.25003ZM8.75 12.75V9.25003H12.25V12.75H8.75Z"
					></path></svg
				>
				Send as a Gift
			</div>
		</div>

		<div class="flex w-[294px] flex-col items-start gap-3">
			{#each features as feat}
				<div class="flex h-[49px] w-full items-center gap-3">
					<img src={Tick} alt="feature icon" class="h-4 w-4" />
					<span class="font-inter flex-1 text-[15px] font-medium leading-[25px] text-white">
						{feat}
					</span>
				</div>
			{/each}
		</div>
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

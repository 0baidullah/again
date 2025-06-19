<script>
	export let icon;
	export let tier;
	export let title;
	export let price;
	export let buttonText;
	export let giftIcon;
	export let bg;
	export let dp;

	import Tick from '../lib/assets/fi_1008958.png';

	/**
	 * @type {any[]}
	 */
	export let features = [];
	console.log(bg);
</script>

<div
	class="flex h-[639px] flex-col items-start gap-2 rounded-lg border
          border-[rgba(255,255,255,0.1)] p-5
          pb-6 backdrop-blur-[200px]
          sm:h-[636px] sm:gap-6 sm:p-5 {bg}"
>
	<div class="relative flex h-[20px] w-[294px] items-center gap-2">
		<img src={icon} alt="{tier} icon" class="h-5 w-5 {dp} " />
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
		<span
			class="font-inter bg-gradient-to-r from-white via-white/50 to-white/50 bg-clip-text text-[38px] font-semibold leading-[48px] text-transparent"
		>
			{price}
		</span>
	</div>

	<div class="flex w-full flex-col items-center gap-2">
		<div
			class="flex h-[52px] w-full items-center justify-center gap-[20px] rounded-md bg-[rgba(72,71,76,0.79)] p-[16px_28px]"
		>
			<button
				class="font-roboto text-[16px] font-bold uppercase italic leading-[20px] text-[rgba(238,237,238,0.68)]"
			>
				{buttonText}
			</button>
		</div>

		<div class="flex h-[25px] w-[114px] flex-none items-center gap-1">
			<img src={giftIcon} alt="gift icon" class="h-5 w-5" />
			<button
				class="font-inter flex-none text-[15px] font-medium leading-[25px] text-[rgba(255,255,255,0.48)] underline"
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

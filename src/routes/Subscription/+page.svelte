<script>
	import Defaul from '../../lib/assets/Default.png';
	import Tiercard from '../../lib/+Tiercard.svelte';
	import Gift from '../../lib/assets/Gift.png';
	import Contact from '$lib/+Contact.svelte';

	const plans = [
		{
			icon: '/tier0.png',
			tier: 'Tier 0',
			title: 'Public',
			price: 'Free',
			isCurrent: true,
			buttonText: 'Current Plan',
			giftIcon: Gift,
			bg: 'bg-[linear-gradient(0deg,rgba(8,6,10,0.44),rgba(8,6,10,0.44)),radial-gradient(160.5%_100%_at_50%_0%,rgba(8,6,10,0.05)_25.18%,rgba(231,223,216,0.05)_100%)]',
			dp: '',
			features: [
				'Access to 100+ public servers',
				' Monthly public car update',
				'Help & Faq support'
			]
		},
		{
			icon: '/tier0.png',
			tier: 'Tier 1',
			title: 'Public+',
			price: '$3.99/month',
			buttonText: 'Upgrade',
			giftIcon: Gift,
			bg: 'bg-[linear-gradient(0deg,rgba(8,6,10,0.15),rgba(8,6,10,0.15)),radial-gradient(160.5%_100%_at_50%_0%,rgba(8,6,10,0.02)_25.18%,rgba(231,223,216,0.02)_100%)]',
			features: [
				'Access to “Public Pack” Servers',
				' In-Game Badges',
				'VIP Alternative and Drift Servers',
				'Priority Queue for Server Hosting'
			],
			dp: 'shadow-[0_0_20px_0_rgba(255,255,255,0.7)]'
		},
		{
			icon: '/Tier3.png',
			tier: 'Tier 0',
			title: 'Midnight',
			price: '$7.99/month',
			isCurrent: true,
			buttonText: 'Current Plan',
			giftIcon: Gift,
			features: [
				'Access to 100+ public servers',
				' Monthly public car update',
				'Help & Faq support',
				'Priority Queue for Server Hosting',
				'Priority Queue for Server Hosting'
			],
			bg: 'bg-[radial-gradient(160.5%_100%_at_50%_0%,rgba(8,6,10,0.05)_25.18%,rgba(255,129,38,0.05)_100%)]',
			dp: 'shadow-[0_0_20px_0_rgba(255,129,38,0.7)]'
		},
		{
			icon: '/Tier4.png',
			tier: 'Tier 1',
			title: 'Underground',
			price: '$12.99',
			buttonText: 'Upgrade',
			giftIcon: Gift,
			features: [
				'Access to 100+ public servers',
				' Monthly public car update',
				'Help & Faq support',
				'Priority Queue for Server Hosting',
				'Priority Queue for Server Hosting',
				'Priority Queue for Server Hosting'
			],
			bg: 'bg-[radial-gradient(160.5%_100%_at_50%_0%,rgba(8,6,10,0.22)_25.18%,rgba(254,44,85,0.22)_100%)]',
			dp: 'shadow-[0_0_20px_0_rgba(221,3,85,0.7)]  '
		}
		// Add 2 more plans as needed...
	];

	let selectedPlan = 'monthly';

	// @ts-ignore
	function setSelectedPlan(plan) {
		selectedPlan = plan;
	}
</script>

<div class=" flex items-center justify-center">
	<div><img src={Defaul} alt="Default" class="back" /></div>
	<div class="b mt-24 flex w-[95%] flex-col items-center justify-center gap-1">
		<div
			class="flex w-full flex-col items-center justify-center rounded-md p-4 sm:flex-row sm:gap-2.5"
		>
			<div class="SI font-bold">JOIN</div>
			<div class="SI font-bold text-pink-700">28,643</div>
			<div class="SI font-bold">OTHERS</div>
		</div>
		<div class="SI">ON no hesi vip</div>
		<div class="SE">Enhance Your No Hesi Experience With VIP</div>
	</div>
</div>
<div class="flex items-center justify-center">
	<div class=" mt-6 flex flex-col items-center justify-center gap-1 py-1">
		<div class=" flex items-center justify-center">
			<div class="relative z-[2] flex rounded-lg bg-gray-900 p-1">
				<button class="btn rounded-md bg-white text-black"> Monthly </button>
				<button class="btn rounded-md"> Annual </button>
				<!-- make a badeg of 20% dsisocn -->
				<div class="badge rounded-4xl absolute bottom-8 left-60 bg-green-400 text-black">
					save 20%
				</div>
			</div>
		</div>
		<div class="text-white">Cant chose ? compare planes ></div>
	</div>
</div>

<div
	class=" mt-12 grid grid-cols-1 gap-6 px-4 sm:grid-cols-2 sm:px-8 lg:grid-cols-2 lg:gap-2 xl:grid-cols-4"
>
	<!-- <div
		class="flex h-[639px] flex-col items-start gap-2 rounded-lg border
            border-[rgba(255,255,255,0.1)] bg-[rgba(8,6,10,0.8)] p-5
            pb-6 backdrop-blur-[100px]
            sm:h-[636px] sm:gap-6 sm:p-5"
	>
		<div class="relative flex h-[20px] w-[294px] items-center gap-2">
			<img src={Tier0} alt="Tier 0 icon" class="h-5 w-5" />
			<span
				class="font-roboto flex-1 text-[16px] font-bold uppercase
                 italic leading-[20px] tracking-[.15em] text-[rgba(238,237,238,0.87)]"
			>
				Tier 0
			</span>
		</div>

		<div class="flex h-[76px] w-[294px] flex-col items-start gap-1">
			<span
				class="font-inter text-[20px] font-semibold leading-[24px]
                 text-[rgba(238,237,238,0.87)]"
			>
				Public
			</span>
			<span
				class="font-inter bg-gradient-to-r from-white via-white/50
                 to-white/50 bg-clip-text text-[38px] font-semibold
                 leading-[48px] text-transparent"
			>
				Free
			</span>
		</div>
		<div class="flex w-full flex-col items-center gap-2">
			<div
				class="md:w[294px] flex h-[52px] w-full items-center justify-center gap-[20px] rounded-md
              bg-[rgba(72,71,76,0.79)] p-[16px_28px]"
			>
				<button
					class="font-roboto text-[16px] font-bold uppercase
                   italic leading-[20px] text-[rgba(238,237,238,0.68)]"
				>
					current plan
				</button>
			</div>

			<div class="flex h-[25px] w-[114px] flex-none items-center gap-1">
				<img src={Gift} alt="Tier 0 icon" class="h-5 w-5" />
				<button
					class="font-inter flex-none text-[15px] font-medium
                     leading-[25px] text-[rgba(255,255,255,0.48)] underline"
				>
					Send as a Gift
				</button>
			</div>
		</div>
		<div class="flex w-[294px] flex-col items-start gap-3">
			<div class="flex h-[49px] w-full items-center gap-3">
				<img src={Tick} alt="Tier 0 icon" class="h-5 w-5" />
				<span
					class="font-inter flex-1 text-[15px] font-medium
                   leading-[25px] text-[rgba(238,237,238,0.87)]"
				>
					Access to 100+ public servers
				</span>
			</div>
		</div>
	</div> -->

	{#each plans as plan}
		<Tiercard {...plan} />
	{/each}
</div>

<div class="mx-8 mt-12 grid rounded-lg bg-[#08060A] md:grid-cols-2 lg:grid-cols-4 2xl:grid-cols-5">
	<div class="hidden flex-col rounded-xl bg-[#08060A] text-white shadow 2xl:flex">
		<div class="sticky top-20 flex h-[7.3rem] flex-col gap-2 self-stretch bg-[#08060A] p-3"></div>
		<p
			class="font-inter-tight flex h-12 w-full items-center border-b border-t border-[rgba(255,255,255,0.1)] pb-4 pt-3 text-[18px] font-extrabold"
		>
			Features
		</p>
		<ul>
			<li
				class="  font-inter-tight flex h-12 w-full items-center border-b border-[rgba(255,255,255,0.1)] pb-4 pt-3 text-sm"
			>
				Acces to Help and Faq
			</li>
			<li
				class="  font-inter-tight flex h-12 w-full items-center border-b border-[rgba(255,255,255,0.1)] pb-4 pt-3 text-sm"
			>
				Acces to Help and Faq
			</li>
			<li
				class="  font-inter-tight flex h-12 w-full items-center border-b border-[rgba(255,255,255,0.1)] pb-4 pt-3 text-sm"
			>
				Acces to Help and Faq
			</li>
			<li
				class="  font-inter-tight flex h-12 w-full items-center border-b border-[rgba(255,255,255,0.1)] pb-4 pt-3 text-sm"
			>
				Acces to Help and Faq
			</li>
			<li
				class="  font-inter-tight flex h-12 w-full items-center border-b border-[rgba(255,255,255,0.1)] pb-4 pt-3 text-sm"
			>
				Acces to Help and Faq
			</li>
			<li
				class="  font-inter-tight flex h-12 w-full items-center border-b border-[rgba(255,255,255,0.1)] pb-4 pt-3 text-sm"
			>
				Acces to Help and Faq
			</li>
			<li
				class="  font-inter-tight flex h-12 w-full items-center border-b border-[rgba(255,255,255,0.1)] pb-4 pt-3 text-sm"
			>
				Acces to Help and Faq
			</li>
			<li
				class="  font-inter-tight flex h-12 w-full items-center border-b border-[rgba(255,255,255,0.1)] pb-4 pt-3 text-sm"
			>
				Acces to Help and Faq
			</li>
			<li
				class="  font-inter-tight flex h-12 w-full items-center border-b border-[rgba(255,255,255,0.1)] pb-4 pt-3 text-sm"
			>
				Acces to Help and Faq
			</li>
			<li
				class="  font-inter-tight flex h-12 w-full items-center border-b border-[rgba(255,255,255,0.1)] pb-4 pt-3 text-sm"
			>
				Acces to Help and Faq
			</li>
			<li
				class="  font-inter-tight flex h-12 w-full items-center border-b border-[rgba(255,255,255,0.1)] pb-4 pt-3 text-sm"
			>
				Acces to Help and Faq
			</li>
			<li
				class="  font-inter-tight flex h-12 w-full items-center border-b border-[rgba(255,255,255,0.1)] pb-4 pt-3 text-sm"
			>
				Acces to Help and Faq
			</li>
			<li
				class="  font-inter-tight flex h-12 w-full items-center border-b border-[rgba(255,255,255,0.1)] pb-4 pt-3 text-sm"
			>
				Acces to Help and Faq
			</li>
			<li
				class="  font-inter-tight flex h-12 w-full items-center border-b border-[rgba(255,255,255,0.1)] pb-4 pt-3 text-sm"
			>
				Acces to Help and Faq
			</li>
			<li
				class="  font-inter-tight flex h-12 w-full items-center border-b border-[rgba(255,255,255,0.1)] pb-4 pt-3 text-sm"
			>
				Acces to Help and Faq
			</li>
		</ul>
		<p
			class="font-inter-tight flex h-12 w-full items-center border-b border-[rgba(255,255,255,0.1)] pb-4 pt-3 text-[18px] font-extrabold"
		>
			Server Hosting
		</p>
		<ul class="space-y-0">
			<li
				class=" font-inter-tight flex h-12 w-full items-center border-b border-[rgba(255,255,255,0.1)] pb-4 pt-3 text-sm"
			></li>
		</ul>
	</div>
	<div class="flex flex-col rounded-xl">
		<div
			class="sticky top-12 z-10 flex flex-col gap-3 self-stretch rounded-t-2xl bg-[#08060A] p-3 2xl:top-20"
		>
			<div class="flex items-center gap-2 2xl:justify-center">
				<div class="">
					<img src="/tier0.png" alt=" icon" class="h-5 w-5" />
				</div>
				<p class="text-md font-roboto font-bold uppercase">Tier 0</p>
			</div>
			<button
				class="font-roboto flex justify-center whitespace-nowrap rounded-xl bg-[#211F23] px-1 py-3 text-xl font-bold italic transition-all duration-300"
				>Current Plan</button
			>
		</div>
		<div
			class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-t border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
		>
			Everything you need to start playing
		</div>

		<ul>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li>
		</ul>
	</div>
	<div class="flex flex-col rounded-xl">
		<div
			class="sticky top-12 z-10 flex flex-col gap-3 self-stretch rounded-t-2xl bg-[#08060A] p-3 2xl:top-20"
		>
			<div class="flex items-center gap-2 2xl:justify-center">
				<div class="">
					<img src="/tier0.png" alt=" icon" class="h-5 w-5 " />
				</div>
				<p class="text-md font-roboto font-bold uppercase">Tier 1</p>
			</div>
			<button
				class="font-roboto flex justify-center whitespace-nowrap rounded-xl bg-white px-1 py-3 text-xl font-bold italic text-black transition-all duration-300"
			>SUBSCRIPTION</button>
		</div>
		<div
			class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-t border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
		>
			Everything you need to start playing
		</div>

		<ul>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
            <li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li>
            <li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li>
            <li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li>
            <li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li>
            <li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li>
            <li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li>
            <li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li>
            <li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li>
            <li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li>
            <li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li>
		</ul>
	</div>
	<div class="flex flex-col rounded-xl">
		<div
			class="sticky top-12 z-10 flex flex-col gap-3 self-stretch rounded-t-2xl bg-[#08060A] p-3 2xl:top-20"
		>
			<div class="flex items-center gap-2 2xl:justify-center">
				<div class="">
					<img src="/Tier3.png" alt=" icon" class="h-5 w-5" />
				</div>
				<p class="text-md font-roboto font-bold uppercase">Tier 2</p>
			</div>
			<button
				class="font-roboto flex justify-center whitespace-nowrap rounded-xl bg-white px-1 py-3 text-xl font-bold italic text-black transition-all duration-300"
			>FREE 7-DAYS TRIAL</button>
		</div>
		<div
			class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-t border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
		>
			Everything you need to start playing
		</div>

		<ul>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
            <li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li><li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li><li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li><li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li><li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li><li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li><li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li><li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
			</li>
		</ul>
	</div>
	<div class="flex flex-col rounded-xl">
		<div
			class="sticky top-12 z-10 flex flex-col gap-3 self-stretch rounded-t-2xl bg-[#08060A] p-3 2xl:top-20"
		>
			<div class="flex items-center gap-2 2xl:justify-center">
				<div class="">
					<img src="/Tier4.png" alt=" icon" class="h-5 w-5" />
				</div>
				<p class="text-md font-roboto font-bold uppercase">Tier 3</p>
			</div>
			<button
				class="font-roboto flex justify-center whitespace-nowrap rounded-xl bg-white px-1 py-3 text-xl font-bold italic text-black transition-all duration-300"
			>SUBSCRIPTION</button>
		</div>
		<div
			class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-t border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
		>
			Everything you need to start playing
		</div>

		<ul>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
			<li
				class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
			>
				<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
			</li>
		</ul>
	</div>
</div>

<Contact />

<style>
	.back {
		@media (max-width: 2800px) {
			position: absolute;
			top: 90px;
			left: 500px;
			width: 800px;
			height: 800px;
			opacity: 100%;
			transform: rotate(75deg);
			z-index: 0;
		}
		@media (max-width: 1440px) {
			position: absolute;
			top: 90px;
			left: 300px;
			width: 800px;
			height: 800px;
			opacity: 100%;
			transform: rotate(75deg);
			z-index: 0;
		}
		@media (max-width: 1240px) {
			position: absolute;
			top: 110px;
			left: 280px;
			width: 350px;
			height: 350px;
			opacity: 100%;
			transform: rotate(75deg);
			z-index: 0;
		}

		@media (max-width: 1024px) {
			position: absolute;
			top: 110px;
			left: 280px;
			width: 350px;
			height: 350px;
			opacity: 100%;
			transform: rotate(75deg);
			z-index: 0;
		}
		@media (max-width: 768px) {
			position: absolute;
			top: 110px;
			left: 200px;
			width: 350px;
			height: 350px;
			opacity: 100%;
			/* transform: rotate(75deg); */
			z-index: 0;
		}
		@media (max-width: 636px) {
			position: absolute;
			top: 110px;
			left: 150px;
			width: 350px;
			height: 350px;
			opacity: 100%;
			/* transform: rotate(75deg); */
			z-index: 0;
		}
		@media (max-width: 536px) {
			position: absolute;
			top: 110px;
			left: 100px;
			width: 280px;
			height: 280px;
			opacity: 100%;
			/* transform: rotate(75deg); */
			z-index: 0;
		}
		@media (max-width: 462px) {
			position: absolute;
			top: 110px;
			left: 70px;
			width: 250px;
			height: 250px;
			opacity: 100%;
			/* transform: rotate(75deg); */
			z-index: 0;
		}
		@media (max-width: 425px) {
			position: absolute;
			top: 190px;
			left: 80px;
			width: 250px;
			height: 250px;
			opacity: 100%;
			/* transform: rotate(75deg); */
			z-index: 0;
		}
		@media (max-width: 375px) {
			position: absolute;
			top: 190px;
			left: 60px;
			width: 250px;
			height: 250px;
			opacity: 100%;
			/* transform: rotate(75deg); */
			z-index: 0;
		}
		@media (max-width: 320px) {
			position: absolute;
			top: 190px;
			left: 50px;
			width: 230px;
			height: 230px;
			opacity: 100%;
			/* transform: rotate(75deg); */
			z-index: 0;
		}

		/*
		@media (max-width: 425px) {
			position: absolute;
			top: 190px;
			left: 80px;
			width: 250px;
			height: 250px;
			opacity: 100%;
			transform: rotate(75deg);
			z-index: 0;
			border: 1px solid black;
			background: #ffffff;
		}
		@media (max-width: 768px) {
			position: absolute;
			top: 110px;
			left: 200px;
			width: 350px;
			height: 350px;
			opacity: 100%;
			transform: rotate(75deg);
			z-index: 0;
			border: 1px solid black;
			background: #ffffff;
		}
		@media (max-width: 1024px) {
			position: absolute;
			top: 110px;
			left: 280px;
			width: 350px;
			height: 350px;
			opacity: 100%;
			transform: rotate(75deg);
			z-index: 0;
			border: 1px solid black;
			background: #ffffff;
		} */
		/* @media (max-width: 1440px) {
			position: absolute;
			top: 90px;
			left: 300px;
			width: 800px;
			height: 800px;
			opacity: 100%;
			transform: rotate(75deg);
			z-index: 0;
			border: 1px solid black;
			background-color: #6aff67;
		} */
	}
	.SI {
		font-size: 64px;
		font-family: 'Roboto flex';
		font-weight: 1000;
		text-transform: uppercase;

		@media (max-width: 320px) {
			font-size: 30px;
		}

		@media (max-width: 375px) {
			font-size: 30px;
		}

		@media (max-width: 475px) {
			font-size: 30px;
		}
		@media (max-width: 495px) {
			font-size: 30px;
		}
		@media (max-width: 515px) {
			font-size: 30px;
		}
	}
	.SE {
		font-size: 17px;
		color: #ffffff;
		font-family: 'Inter Tight';
		font-weight: 400;
		text-align: center;
	}
	.btn {
		width: 150px;
		height: 36px;

		@media (max-width: 320px) {
			width: 130px;
			height: 36px;
		}
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
	/* Frame 53 */

	/* Auto layout */
	/* display: flex;
flex-direction: column;
align-items: center;
padding: 24px 0px 0px;
gap: 16px;

width: 1368px;
height: 208px;


/* Inside auto layout */
	/* flex: none;
order: 1;
flex-grow: 0;
z-index: 4; */
</style>

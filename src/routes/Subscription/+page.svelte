<script>
	import Defaul from '../../lib/assets/Default.png';
	import Tiercard from '../../lib/+Tiercard.svelte';
	import Gift from '../../lib/assets/Gift.png';
	import Contact from '$lib/+Contact.svelte';
	import Limts from '../../lib/+Limits.svelte';
	import Limits from '../../lib/+Limits.svelte';

	const plans = [
		{
			icon: '/tier0.png',
			tier: 'Tier 0',
			title: 'Public',
			price: 'Free',
			anuallayprice: 'Free',
			isCurrent: true,
			buttonText: 'Current Plan',
			giftIcon: Gift,
			bg: 'bg-[linear-gradient(0deg,rgba(8,6,10,0.44),rgba(8,6,10,0.44)),radial-gradient(160.5%_100%_at_50%_0%,rgba(8,6,10,0.05)_25.18%,rgba(231,223,216,0.05)_100%)]',
			dp: '',
			features: [
				'Access to 100+ public servers',
				' monthly public car update',
				'Help & Faq support'
			],
			btn: 'bg-[rgba(72,71,76,0.79)] p-[16px_28px] text-white '
		},
		{
			icon: '/tier0.png',
			tier: 'Tier 1',
			title: 'Public+',
			price: '$3.99',
			anuallayprice: '$2.99',
			buttonText: 'Upgrade',
			giftIcon: Gift,
			bg: 'bg-[linear-gradient(0deg,rgba(8,6,10,0.15),rgba(8,6,10,0.15)),radial-gradient(160.5%_100%_at_50%_0%,rgba(8,6,10,0.02)_25.18%,rgba(231,223,216,0.02)_100%)]',
			features: [
				'Access to “Public Pack” Servers',
				' In-Game Badges',
				'VIP Alternative and Drift Servers',
				'Priority Queue for Server Hosting'
			],
			dp: '',
			// dp: 'shadow-[0_0_20px_0_rgba(255,255,255,0.7)]'
			btn: 'bg-white text-black '
		},
		{
			icon: '/Tier3.png',
			tier: 'Tier 2',
			title: 'Midnight',
			price: '$7.99',
			anuallayprice: '$5.58',
			isCurrent: true,
			buttonText: 'Current Plan',
			giftIcon: Gift,
			features: [
				'Access to 100+ public servers',
				' monthly public car update',
				'Help & Faq support',
				'Priority Queue for Server Hosting',
				'Priority Queue for Server Hosting'
			],
			bg: 'bg-[radial-gradient(160.5%_100%_at_50%_0%,rgba(8,6,10,0.05)_25.18%,rgba(255,129,38,0.05)_100%)]',
			dp: '',
			btn: 'bg-white text-black '
			// dp: 'shadow-[0_0_20px_0_rgba(255,129,38,0.7)]'
		},
		{
			icon: '/Tier4.png',
			tier: 'Tier 3',
			title: 'Underground',
			price: '$12.99',
			anuallayprice: '$6.67',
			buttonText: 'Upgrade',
			giftIcon: Gift,
			features: [
				'Access to 100+ public servers',
				' monthly public car update',
				'Help & Faq support',
				'Priority Queue for Server Hosting',
				'Priority Queue for Server Hosting',
				'Priority Queue for Server Hosting'
			],
			bg: 'bg-[radial-gradient(160.5%_100%_at_50%_0%,rgba(8,6,10,0.22)_25.18%,rgba(254,44,85,0.22)_100%)]',
			dp: '',
			btn: 'bg-white text-black '
			// dp: 'shadow-[0_0_20px_0_rgba(221,3,85,0.7)]  '
		}
		// Add 2 more plans as needed...
	];

	let selected = 'monthly';
	// @ts-ignore
	function select(type) {
		selected = type;
	}

	let memberCount = '28643';

	/**
	 * @param {string | any[]} str
	 */
	function formatIndianComma(str) {
		// e.g. '28643'
		const last3 = str.slice(-3); // '643'
		const rest = str.slice(0, -3); // '28'
		// @ts-ignore
		const commaedRest = rest.replace(/\B(?=(\d{2})+(?!\d))/g, ',');
		return (commaedRest ? commaedRest + ',' : '') + last3;
	}

	let formatted = formatIndianComma(memberCount); // => "28,643"
	let digits = formatted.split(''); // => ['2','8',',','6','4','3']
</script>

<div class=" flex items-center justify-center">
	<div><img src={Defaul} alt="Default" class="back" /></div>
	<div class="b mt-24 flex w-[95%] flex-col items-center justify-center gap-1">
		<div class="flex w-full flex-col items-center justify-center rounded-md sm:flex-row sm:gap-2">
			<div class="SI font-bold">JOIN</div>
			<div class="SI font-bold text-[#dd0355] sm:hidden">28,643</div>

			<span class="hidden sm:flex">
				{#each digits as char, i}
					{#if char === ','}
						<span class="comma">,</span>
					{:else}
						<div class="roller">
							<div
								class="roller-digit"
								style="transform: translateY(-{parseInt(char) * 3.5}rem); 
											"
							>
								<div class="">
									{#each Array(10) as _, j}
										<div class="digit-row">{j}</div>
									{/each}
								</div>
							</div>
						</div>
					{/if}
				{/each}
			</span>

			<div class="SI font-bold">OTHERS</div>
		</div>
		<div class="SI">ON no hesi vip</div>
		<div class="SE">Enhance Your No Hesi Experience With VIP</div>
	</div>
</div>

<div class="flex items-center justify-center">
	<div class="mt-6 flex flex-col items-center justify-center gap-1 py-1">
		<div class="flex items-center justify-center">
			<div class="relative z-[2] flex rounded-lg bg-[rgba(8,6,10,0.83)] p-1">
				<button
					class="btn duration-400 rounded-md px-4 py-2 transition-colors"
					class:bg-white={selected === 'monthly'}
					class:text-black={selected === 'monthly'}
					class:bg-transparent={selected !== 'monthly'}
					class:text-white={selected !== 'monthly'}
					on:click={() => select('monthly')}
				>
					Monthly
				</button>

				<button
					class="btn rounded-md px-4 py-2 transition-colors duration-300"
					class:bg-white={selected === 'annualy'}
					class:text-black={selected === 'annualy'}
					class:bg-transparent={selected !== 'annualy'}
					class:text-white={selected !== 'annualy'}
					on:click={() => select('annualy')}
				>
					Annual
				</button>

				<div
					class="badge absolute bottom-8 left-24 rounded-2xl bg-green-400 px-2 py-1 text-sm text-black"
				>
					Save 20%
				</div>
			</div>
		</div>
		<div class="group inline-block cursor-pointer text-white hover:underline">
			Can't choose? Compare plans
			<span class="inline-block transition-transform duration-200 group-hover:translate-x-2"
				>&gt;</span
			>
		</div>
	</div>
</div>

<div
	class=" mt-12 grid grid-cols-1 gap-6 px-4 sm:grid-cols-2 sm:px-8 lg:grid-cols-2 lg:gap-2 xl:grid-cols-4"
>
	{#each plans as plan}
		<Tiercard
			{...plan}
			selectedPrice={selected === 'monthly' ? plan.price : plan.anuallayprice}
			selectedType={selected}
		/>
	{/each}
</div>

<!-- <div class="mx-8 mt-12 grid rounded-lg bg-[#08060A] md:grid-cols-2 lg:grid-cols-4 2xl:grid-cols-5">
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
				<p class="text-md font-roboto font-bold uppercase">Tier 1</p>
			</div>
			<button
				class="font-roboto flex justify-center whitespace-nowrap rounded-xl bg-white px-1 py-3 text-xl font-bold italic text-black transition-all duration-300"
				>SUBSCRIPTION</button
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
				>FREE 7-DAYS TRIAL</button
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
				>SUBSCRIPTION</button
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
		</ul>
	</div>
</div> -->

<Limits />
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
		/* font-family: 'Roboto flex'; */
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
		/* font-family: 'Inter Tight'; */
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

	.comma {
		display: inline-block;
		font-size: 64px;
		line-height: 4rem;
		margin: 0 0.1rem;
		vertical-align: bottom;
		color: #dd0355;
		font-weight: 1000;
	}

	.roller {
		display: flex;
		justify-content: center;
		height: 60px;
		width: 48px;
		display: inline-block;
		position: relative;
		border-radius: 0.25rem;
		overflow: hidden;
	}

	.roller-digit {
		width: 47px;
		height: 3rem;
		display: flex;
		flex-direction: column;
		position: absolute;
		animation: rollDownBounce 0.5s linear forwards;
		/* settleBounce 0.5s ease-in-out 0.6s forwards; */
		/* animation-iteration-count: infinite; */
		/* overflow: hidden; */
	}

	.digit-row {
		height: 56px;
		display: flex;
		align-items: center;
		justify-content: center;
		font-size: 66px;
		color: #dd0355;
		font-weight: 1000;
		/*  make digit bounce  */
		animation: bounce 1.5s linear;
	}

	@keyframes bounce {
		0% {
			transform: translateY(0);
		}

		50% {
			transform: translateY(-3.5px);
		}

		75% {
			transform: translateY(0px);
		}
		90% {
			transform: translateY(-3.5px);
		}
		100% {
			transform: translateY(0);
		}
	}
	/* .roller-digit > .digit-row:nth-child(odd) {
		background-color: rgba(221, 3, 85, 0.1);
	}
	.roller-digit > .digit-row:nth-child(even) {
		background-color: rgba(221, 3, 85, 0.2);
	}
	.roller-digit > .digit-row:nth-child(10) {
		background-color: rgba(221, 3, 85, 0.3);
	}
	.roller-digit > .digit-row:nth-child(11) {
		background-color: rgba(221, 3, 85, 0.4);
	}
	.roller-digit > .digit-row:nth-child(12) {
		background-color: rgba(221, 3, 85, 0.5);
	}

	.roller-digit > .digit-row:nth-child(13) {
		background-color: rgba(221, 3, 85, 0.6);
	} */

	@keyframes rollDownBounce {
		0% {
			transform: translateY(calc(-10 * 3.5rem));
			/* transform: translateY(-35rem); */
		}
		90% {
			/* transform: translateY(-10px); */
		}
		100% {
			/* transform: translateY(0); */
		}
	}

	@keyframes settleBounce {
		0% {
		}
		80% {
			/* transform: translateY(-3.5rem); */
		}
		100% {
		}
	}
</style>

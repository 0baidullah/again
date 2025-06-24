<script>
// @ts-nocheck

	import Defaul from '../../lib/assets/Default.png';
	import Tiercard from '../../lib/+Tiercard.svelte';
	import Gift from '../../lib/assets/Gift.png';
	import Contact from '$lib/+Contact.svelte';
	import Limts from '../../lib/+Limits.svelte';
	import Limits from '../../lib/+Limits.svelte';
	import MobileLimts from '../../lib/+Mobile.svelte';
	import Mobile from '../../lib/+Mobile.svelte';
	  import { onMount, onDestroy } from 'svelte';



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
			btn: 'bg-[rgba(72,71,76,0.79)] p-[16px_28px] text-white ',
			month: '',
			discount:'-20%'
		},
		{
			icon: '/tier0.png',
			tier: 'Tier 1',
			title: 'Public',
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

			dp: 'drop-shadow-[0_0_20px_rgba(255,255,255,0.7)]',
			btn: 'bg-white text-black hover:shadow-[0_0_10px_2px_rgba(255,255,255,0.5)] transition-all duration-300 ',
			month: '/month',
			discount:'-20%'
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

			btn: 'bg-white text-black hover:shadow-[0_0_10px_2px_rgba(255,255,255,0.5)] transition-all duration-300 ',
			dp: 'drop-shadow-[0_0_20px_rgba(255,129,38,0.7)]',
			month: '/month'
			,discount:'-20%'
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
			btn: 'bg-white text-black hover:shadow-[0_0_10px_2px_rgba(255,255,255,0.5)] transition-all duration-300 ',
			month: '/month',
			dp: 'drop-shadow-[0_0_20px_rgba(221,3,85,0.7)]',
			discount:'-40%'
		}
		// Add 2 more plans as needed...
	];

	let selected = 'month';
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

	let formatted = formatIndianComma(memberCount);
	let digits = formatted.split('');



//  let isMobile = true;

//   function checkScreen() {
//     isMobile = window.innerWidth <= 1024;
//   }

//   onMount(() => {
//     checkScreen();
//     window.addEventListener('resize', checkScreen);
//   });

//   onDestroy(() => {
//     window.removeEventListener('resize', checkScreen);
//   });


let isMobile = false;

  onMount(() => {
    const mediaQuery = window.matchMedia('(max-width: 1024px)');

    // Initial value
    isMobile = mediaQuery.matches;

    // Update on screen resize
	// @ts-ignore
	const handler = (event) => {
	  isMobile = event.matches;
	};

    mediaQuery.addEventListener('change', handler);

    // Cleanup
    return () => {
      mediaQuery.removeEventListener('change', handler);
    };
  });
let width;
  
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
					class="btn duration-400 cursor-pointer rounded-md px-4 py-2 transition-colors delay-150"
					class:bg-white={selected === 'month'}
					class:text-black={selected === 'month'}
					class:bg-transparent={selected !== 'month'}
					class:text-white={selected !== 'month'}
					on:click={() => select('month')}
				>
					Monthly
				</button>

				<button
					class="btn cursor-pointer rounded-md px-4 py-2 transition-colors duration-300"
					class:bg-white={selected === 'annualy'}
					class:text-black={selected === 'annualy'}
					class:bg-transparent={selected !== 'annualy'}
					class:text-white={selected !== 'annualy'}
					on:click={() => select('annualy')}
				>
					Annual
				</button>

				<div
					class="badge absolute  bottom-8 left-60 rounded-2xl bg-[#6aff67] py-1 px-1 text-[10px] text-black"
				>
					Save 20%
				</div>
			</div>
		</div>
		<div class="group inline-flex cursor-pointer items-center gap-1">
			Can't choose? Compare plans
			<img
				src="/leftarrow.png"
				alt="arrow"
				class="h-2 w-2 cursor-pointer brightness-0 contrast-200 invert filter transition-transform duration-600 group-hover:translate-x-[5px]"
			/>
		</div>
	</div>
</div>

<div
	class=" mt-12 grid grid-cols-1 gap-3 lg:gap-1 px-4 sm:grid-cols-2 sm:px-8 lg:grid-cols-2  xl:grid-cols-4"
>
	{#each plans as plan}
		<Tiercard
			{...plan}
			selectedPrice={selected === 'month' ? plan.price : plan.anuallayprice}
			selectedType={selected}
		/>
	{/each}
</div>

 {#if width > 1024}
 <Limits />
 <!-- {:else if width < 768}
 <MobileLimits/> -->
 {:else}
 <MobileLimts/>
 
{/if}
<Contact />


<svelte:window bind:innerWidth={width} />
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
			z-index: -50;
		}
		@media (max-width: 1440px) {
			position: absolute;
			top: 90px;
			left: 300px;
			width: 800px;
			height: 800px;
			opacity: 100%;
			transform: rotate(75deg);
			z-index: -50;
		}
		@media (max-width: 1240px) {
			position: absolute;
			top: 110px;
			left: 280px;
			width: 350px;
			height: 350px;
			opacity: 100%;
			transform: rotate(75deg);
			z-index: -50;
		}

		@media (max-width: 1024px) {
			position: absolute;
			top: 110px;
			left: 280px;
			width: 350px;
			height: 350px;
			opacity: 100%;
			transform: rotate(75deg);
			z-index: -50;
		}
		@media (max-width: 768px) {
			position: absolute;
			top: 110px;
			left: 200px;
			width: 350px;
			height: 350px;
			opacity: 100%;
			/* transform: rotate(75deg); */
			z-index: -50;
		}
		@media (max-width: 636px) {
			position: absolute;
			top: 110px;
			left: 150px;
			width: 350px;
			height: 350px;
			opacity: 100%;
			/* transform: rotate(75deg); */
			z-index: -50;
		}
		@media (max-width: 536px) {
			position: absolute;
			top: 110px;
			left: 100px;
			width: 280px;
			height: 280px;
			opacity: 100%;
			/* transform: rotate(75deg); */
			z-index: -50;
		}
		@media (max-width: 462px) {
			position: absolute;
			top: 110px;
			left: 70px;
			width: 250px;
			height: 250px;
			opacity: 100%;
			/* transform: rotate(75deg); */
			z-index: -50;
		}
		@media (max-width: 425px) {
			position: absolute;
			top: 190px;
			left: 80px;
			width: 250px;
			height: 250px;
			opacity: 100%;
			/* transform: rotate(75deg); */
			z-index: -50;
		}
		@media (max-width: 375px) {
			position: absolute;
			top: 190px;
			left: 60px;
			width: 250px;
			height: 250px;
			opacity: 100%;
			/* transform: rotate(75deg); */
			z-index: -50;
		}
		@media (max-width: 320px) {
			position: absolute;
			top: 190px;
			left: 50px;
			width: 230px;
			height: 230px;
			opacity: 100%;
			/* transform: rotate(75deg); */
			z-index: -50;
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
@media (max-width: 320px) {
	font-size: 14px;
}

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
		
		@media (max-width: 320px) {
			width: 50px;
			height: 16px;
			font-size: 8px;
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

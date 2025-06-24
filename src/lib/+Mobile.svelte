<script>
	const tiers = [
		{
			name: 'Tier 0',
			icon: '/tier0.png',
			price: 'Free',
			description: 'Everything you need to start playing.',
			badge: 'Current Plan',
			btn: 'bg-[rgba(72,71,76,0.79)] p-[16px_28px] text-white ',
			features: [
				'Acces to Help and Help FAQ',
				'Monthly Public Car Update',
				'Access to 100+ Public server',
				false,
				false,
				false,
				false,
				false,
				false,
				false,
				false,
				false,
				false,
				false,
				false,
				false,
				false,
				false,
				''
			]
		},
		{
			name: 'Tier 1',
			icon: '/tier0.png',
			price: '$3.99/month',
			description: 'Get a taste',
			btn: 'bg-white text-black ',
			badge: 'SUBSCRIPTION',
			features: [
				'Access to Help and Help FAQ ',
				'Monthly Public  Car Update',
				'Acces to Public 100+ Servers',
				'VIP Slots For Public For turned Cars On Servers ',
				'VIP-Only "Public Pack" Servers',
				'VIP ALternative and Drift Servers',
				'In-game badges',
				false,
				false,
				false,
				false,
				false,
				false,
				false,
				false,
				false,
				false,
				false,
				false
			]
		},
		{
			name: 'Tier 2',
			icon: '/Tier3.png',
			price: '$7.99/month',
			description: 'Amplify your experience',
			btn: 'bg-white text-black ',
			badge: 'FREE 7-DAYS TRIAL',
			features: [
				'Access to Help and Help FAQ ',
				'Monthly Public  Car Update',
				'Acces to Public 100+ Servers',
				'VIP Slots For Public For turned Cars On Servers ',
				'VIP-Only "Public Pack" Servers',
				'VIP ALternative and Drift Servers',
				'In-game badges',
				'Spec Cars in Spec Servers',
				'JDM, VTEC and Manual servers',
				'1 new spec car/month',
				'In-game badges',
				'FULL',
				'10',
				'6hr',
				false,
				false,
				false,
				false,
				false
			]
		},
		{
			name: 'Tier 3',
			icon: '/Tier4.png',
			price: '$12.99/month',
			btn: 'bg-white text-black ',
			description: 'Reach new limits',
			badge: 'SUBSCRIPTION',
			features: [
				'Access to Help and Help FAQ ',
				'Monthly Public  Car Update',
				'Acces to Public 100+ Servers',
				'VIP Slots For Public For turned Cars On Servers ',
				'VIP-Only "Public Pack" Servers',
				'VIP ALternative and Drift Servers',
				'In-game badges',
				'Spec Cars in Spec Servers',
				'JDM, VTEC and Manual servers',
				'Complete Servers Access',
				'Community Voring Access',
				'Early Acces to New Map',
				'Exclusive access to Cars on Public servers',
				'Three new  spec cars a month',
				'1 new spec car/month',
				'full',
				'Early Acces to New Map ',
				'',
				false
			]
		}
	];
	const moboile = [
		{
			name: 'Tier 0',
			icon: '/tier0.png',
			price: 'Free',
			description: 'Everything you need to start playing.',
			badge: 'Current Plan',
			btn: 'bg-[rgba(72,71,76,0.79)] p-[16px_28px] text-white ',
			features: [
				'Acces to Help and Help FAQ',
				'Monthly Public Car Update',
				'Access to 100+ Public server'
			]
		},
		{
			name: 'Tier 1',
			icon: '/tier0.png',
			price: '$3.99/month',
			description: 'Get a taste',
			btn: 'bg-white text-black ',
			badge: 'SUBSCRIPTION',
			features: [
				'Access to Help and Help FAQ ',
				'Monthly Public  Car Update',
				'Acces to Public 100+ Servers',
				'VIP Slots For Public For turned Cars On Servers ',
				'VIP-Only "Public Pack" Servers',
				'VIP ALternative and Drift Servers',
				'In-game badges'
			]
		},
		{
			name: 'Tier 2',
			icon: '/Tier3.png',
			price: '$7.99/month',
			description: 'Amplify your experience',
			btn: 'bg-white text-black ',
			badge: 'FREE 7-DAYS TRIAL',
			features: [
				'Access to Help and Help FAQ ',
				'Monthly Public  Car Update',
				'Acces to Public 100+ Servers',
				'VIP Slots For Public For turned Cars On Servers ',
				'VIP-Only "Public Pack" Servers',
				'VIP ALternative and Drift Servers',
				'In-game badges',
				'Spec Cars in Spec Servers',
				'JDM, VTEC and Manual servers',
				'1 new spec car/month',
				'In-game badges',
				'FULL',
				'10',
				'6hr'
			]
		},
		{
			name: 'Tier 3',
			icon: '/Tier4.png',
			price: '$12.99/month',
			btn: 'bg-white text-black ',
			description: 'Reach new limits',
			badge: 'SUBSCRIPTION',
			features: [
				'Access to Help and Help FAQ ',
				'Monthly Public  Car Update',
				'Acces to Public 100+ Servers',
				'VIP Slots For Public For turned Cars On Servers ',
				'VIP-Only "Public Pack" Servers',
				'VIP ALternative and Drift Servers',
				'In-game badges',
				'Spec Cars in Spec Servers',
				'JDM, VTEC and Manual servers',
				'Complete Servers Access',
				'Community Voring Access',
				'Early Acces to New Map',
				'Exclusive access to Cars on Public servers',
				'Three new  spec cars a month',
				'1 new spec car/month',
				'full',
				'Early Acces to New Map ',
				'',
				false
			]
		}
	];

	const featureList = [
        'Access to Help and Help FAQ',
		'Monthly Public Car Updates',
		'Access to 100+ Public Servers',
		'VIP slots for Tuned Cars on Public Servers',
		"VIP-Only 'Public Pack' Servers",
		'VIP Alternative and Drift Servers',
		'In-game Badges',
		'Spec Cars in Spec Servers',
		'JDM, VTEC, and Manual servers',
		'Complete Server Access',
		'Community Voting Access',
		'Early Access to Exclusive Content',
		'Exclusive access to new Maps',
		'Exclusive access to Spec cars on Public servers',
		'One new Spec car a month',
		'Server Creation',
		'Servers per day',
		'Server Queue',
		'Max. Players'
	];
		import { onMount } from 'svelte';
		let width = 0;

		onMount(() => {
			width = window.innerWidth;
			const handleResize = () => {
				width = window.innerWidth;
			};
			window.addEventListener('resize', handleResize);
			return () => window.removeEventListener('resize', handleResize);
		});
</script>

<div class="mx-8 mt-12 grid rounded-lg bg-[#08060A] md:grid-cols-2 lg:grid-cols-4 2xl:grid-cols-5">
	<!-- Sidebar -->
	<div class="hidden flex-col rounded-xl bg-[#08060A] text-white shadow 2xl:flex">
		<div class="sticky top-20 flex h-[7.3rem] flex-col gap-2 self-stretch bg-[#08060A] p-3"></div>
		<p
			class="font-inter-tight flex h-12 w-full items-center border-b border-t border-[rgba(255,255,255,0.1)] pb-4 pt-3 text-[18px] font-extrabold"
		>
			Features
		</p>
		<ul>
			{#each featureList as feature}
				<li
					class="font-inter-tight flex h-12 w-full items-center border-b border-[rgba(255,255,255,0.1)] pb-4 pt-3 text-sm"
				>
					{feature}
				</li>
			{/each}
		</ul>
	</div>

	<!-- Tiers -->

	{#if width > 1024}
		{#each tiers as tier}
			<div class="flex flex-col rounded-xl">
				<div
					class="sticky top-12 z-10 flex flex-col gap-3 self-stretch rounded-t-2xl bg-[#08060A] p-3 2xl:top-20"
				>
					<div class="flex items-center gap-2 2xl:justify-center">
						<img src={tier.icon} alt=" icon" class="h-5 w-5" />
						<p class="text-md font-roboto font-bold uppercase">{tier.name}</p>
					</div>
					<button
						class=" justify-center whitespace-nowrap rounded-xl {tier.btn}  px-1 py-3 text-xl font-bold italic transition-all duration-300"
						>{tier.badge}</button
					>
				</div>
				<div
					class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-t border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
				>
					{tier.description}
				</div>
				<ul>
					{#each tier.features as feat, i}
						<li
							class="font-inter-tight relative top-[5px] flex h-12 items-center justify-start border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-[14px] 2xl:p-0"
						>
							{#if feat === true}
								<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
							{:else if feat === false}
								<span class="text-gray-500">1</span>
							{:else}
								<span>{feat}</span>
							{/if}
						</li>
					{/each}
				</ul>
				<ul>
					{#each tier.features as feat, i}
						<li
							class="font-inter-tight relative top-[5px] flex h-12 items-center justify-start border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-[14px] 2xl:p-0"
						>
							{#if feat === true}
								<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
							{:else if feat === false}
								<span class="text-gray-500"></span>
							{:else}
								<span>{feat}</span>
							{/if}
						</li>
					{/each}
				</ul>
			</div>
		{/each}
	{:else}
		{#each moboile as mob}
			<div class="flex flex-col rounded-xl">
				<div
					class="sticky top-12 z-10 flex flex-col gap-3 self-stretch rounded-t-2xl bg-[#08060A] p-3 2xl:top-20"
				>
					<div class="flex items-center gap-2 2xl:justify-center">
						<img src={mob.icon} alt=" icon" class="h-5 w-5" />
						<p class="text-md font-roboto font-bold uppercase">{mob.name}</p>
					</div>
					<button
						class=" justify-center whitespace-nowrap rounded-xl {mob.btn}  px-1 py-3 text-xl font-bold italic transition-all duration-300"
						>{mob.badge}</button
					>
				</div>
				<div
					class="font-inter-tight relative top-[5px] flex h-12 items-center border-b border-t border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-sm font-semibold 2xl:justify-center 2xl:p-0"
				>
					{mob.description}
				</div>
				<ul>
					{#each mob.features as feat, i}
						<li
							class="font-inter-tight relative top-[5px] flex h-12 items-center justify-start border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-[14px] 2xl:p-0"
						>
							{#if feat === true}
								<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
							{:else if feat === false}
								<span class="text-gray-500">1</span>
							{:else}
								<span>{feat}</span>
							{/if}
						</li>
					{/each}
				</ul>
				<ul>
					{#each mob.features as feat, i}
						<li
							class="font-inter-tight relative top-[5px] flex h-12 items-center justify-start border-b border-[rgba(255,255,255,0.1)] bg-[#08060A] pb-3 text-[14px] 2xl:p-0"
						>
							{#if feat === true}
								<img src="/Tick2.png" alt=" icon" class="h-5 w-5" />
							{:else if feat === false}
								<span class="text-gray-500"></span>
							{:else}
								<span>{feat}</span>
							{/if}
						</li>
					{/each}
				</ul>
			</div>
		{/each}
	{/if}
</div>

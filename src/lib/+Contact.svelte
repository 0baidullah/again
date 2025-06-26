<script lang="ts">
	import { enhance } from '$app/forms';
	import { fade } from 'svelte/transition';
	import { writable } from 'svelte/store';
	import InputField from '../lib/+Limits.svelte';

	// Form schema using Svelte's reactive declarations
	let name = '';
	let email = '';
	let question = '';

	let success = writable<string | null>(null);
	let serverError = writable<string | null>(null);
	let isPending = writable(false);

	// Character counter
	$: questionLength = question.length;

	// Validation functions
	const validateName = () => {
		if (!name) return 'Name is required';
		return '';
	};

	const validateEmail = () => {
		if (!email) return 'Email is required';
		if (!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)) return 'Invalid email address';
		return '';
	};

	const validateQuestion = () => {
		if (!question) return 'Question is required';
		if (question.length > 400) return 'Question must be less than 400 characters';
		return '';
	};

	// Combined validation
	$: nameError = validateName();
	$: emailError = validateEmail();
	$: questionError = validateQuestion();
	$: formValid = !nameError && !emailError && !questionError;

	async function handleSubmit() {
		$isPending = true;
		$serverError = null;
		$success = null;

		try {
			const res = await fetch('/api/contactForm', {
				method: 'POST',
				headers: { 'Content-Type': 'application/json' },
				body: JSON.stringify({ name, email, question })
			});

			if (!res.ok) {
				const errorData = await res.json();
				throw errorData;
			}

			$success = 'Your question has been submitted!';
			name = '';
			email = '';
			question = '';
		} catch (error: any) {
			const errObj =
				typeof error === 'object' && error !== null ? (error as Record<string, any>) : {};
			$serverError =
				errObj.error?.name?.[0] ||
				errObj.error?.email?.[0] ||
				errObj.error?.question?.[0] ||
				'Something went wrong.';
		} finally {
			$isPending = false;
		}
	}
</script>

<div class="mt-28 bg-[#08060A] px-3 py-20 text-white sm:mx-8 md:px-12">
	<div class="flex max-w-full flex-col items-start justify-center gap-7 lg:flex-row">
		<div class="flex-1 text-left">
			<h1
				class="text-2xl font-extrabold uppercase leading-tight text-gray-300 md:text-5xl lg:text-[64px]"
			>
				Questions?
				<br />
				<span class=" text-white">No Problem,</span>
				<br />
				<span class="text-white">
					We Have The <span class=" text-gray-300">Answers.</span>
				</span>
			</h1>
		</div>

		<form
			use:enhance={handleSubmit}
			class="w-full flex-1 space-y-4 rounded-xl border border-[rgba(255,255,255,0.1)] bg-[#08060A] p-6"
		>
			<!-- <div class="text-md rounded border border-yellow-500 bg-yellow-500/20 p-1 text-yellow-400">
				⚠️ We may take up to 24–78 hours to reply
			</div> -->
			<h1
				class="text-3xl font-bold  leading-tight text-gray-300 md:text-5xl lg:text-[64px]"
			>
				Conact us
			</h1>

			{#if $serverError}
				<div
					transition:fade
					class="rounded border border-red-400 bg-red-400/10 p-2 text-sm text-red-400"
				>
					{$serverError}
				</div>
			{/if}

			{#if $success}
				<div
					transition:fade
					class="rounded border border-green-400 bg-green-400/10 p-2 text-sm text-green-400"
				>
					{$success}
				</div>
			{/if}

			<div>
				<!-- svelte-ignore a11y_label_has_associated_control -->
				<label class="mb-1 block text-sm">Name</label>
				<div class="align-center relative flex justify-center">
					<span class="absolute left-3 top-2">
						<img src="/Envelope.png" alt="icon" class="icon-img" />
					</span>
					<input
						type="text"
						bind:value={name}
						placeholder="John Doe"
						class="bg-#0D0B0F w-full rounded border border-[rgba(255,255,255,0.1)] py-3 pl-11 text-sm focus:outline-none focus:ring-2 focus:ring-purple-500"
					/>
				</div>
			</div>
			<div>
				<!-- svelte-ignore a11y_label_has_associated_control -->
				<label class="mb-1 block text-sm">Name</label>
				<div class="align-center relative flex justify-center">
					<span class="absolute left-3 top-2">
						<img src="/User.png" alt="icon" class="icon-img" />
					</span>
					<input
						type="text"
						bind:value={name}
						placeholder="admin@gmail.com"
						class="bg-#0D0B0F w-full rounded border border-[rgba(255,255,255,0.1)] py-3 pl-11 text-sm focus:outline-none focus:ring-2 focus:ring-purple-500"
					/>
				</div>
			</div>
			<div>
				<!-- svelte-ignore a11y_label_has_associated_control -->
				<label class="mb-1 block text-sm">Name</label>
				<div class="align-center relative flex justify-center">
					<span class="absolute left-3 top-2">
						<img src="/Mesaage.png" alt="icon" class="icon-img" />
					</span>
					<!-- svelte-ignore element_invalid_self_closing_tag -->
					<div class="flex w-full flex-col">
						<textarea
							maxlength={1000}
							bind:value={question}
							placeholder=""
							class="bg-#0D0B0F h-50 flex w-full rounded border border-[rgba(255,255,255,0.1)] py-2 pl-11 text-sm focus:outline-none focus:ring-2 focus:ring-purple-700"
						/>
						<!-- {#if questionError}
          <p class="text-red-500 text-xs mt-1">{questionError}</p>
        {/if} -->
						<div class="text-right text-xs text-gray-500">{questionLength}/400</div>
					</div>
				</div>
			</div>

			<!-- <div class="mt-4">
				<div class="w-fit rounded bg-white p-4 text-sm text-black">[reCAPTCHA goes here]</div>
			</div> -->

			<button
				type="submit"
				disabled={!formValid || $isPending}
				class="mt-4 w-full rounded-lg py-2 font-bold uppercase tracking-wide text-white drop-shadow-[0_0_8px_#8800f0] transition"
				style="background: #8800F0;
       hover:box-shadow: 0px 4px 12px 4px rgba(136, 0, 240, 0.2);
             "
			>
				{$isPending ? 'Sending...' : 'Send'}
			</button>
		</form>
	</div>
</div>

<style>
	/* .bg-gray-1000 {
    background-color: #111;
  } */
	input,
	textarea {
		transition:
			border-color 0.2s ease,
			box-shadow 0.2s ease;
	}
	button {
		transition:
			background-color 0.2s ease,
			opacity 0.2s ease;
	}
</style>

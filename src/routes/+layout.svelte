<script>
	import '../app.css';
	import Header from '../lib/+Header.svelte';
	import Contact from '$lib/+Contact.svelte';
</script>

<div class=" " style=" color: white; max-width: 100%; max-height: 100%;">
	<Header />
	<main class=" max-h-full max-w-full">
		<slot />
	</main>
	<Contact/>
</div>

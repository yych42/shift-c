<script>
	import { goto } from '$app/navigation';

	import { onMount } from 'svelte';
	import { fade, fly } from 'svelte/transition';

	let shouldShow = false;

	onMount(() => {
		shouldShow = true;
	});
</script>

{#if shouldShow}
	<h2
		class="-mt-32 text-2xl font-semibold text-gray-800 text-center"
		in:fly={{ y: 5, duration: 1000 }}
		out:fly={{ y: -5, duration: 500 }}
	>
		Your sleep-wake cycle is governed by two forces.<br />
	</h2>
	<div class="flex flex-row space-x-8 my-16">
		<div
			class="flex flex-col justify-center items-center rounded-lg bg-white shadow-md hover:shadow-xl active:shadow-md transition-shadow 
				 border-stone-200 p-8 space-y-8"
			in:fly={{ y: 5, duration: 1000, delay: 1000 }}
		>
			<div>
				<img
					src="https://imagedelivery.net/4v3KB3Aeo_3sLg3kKoifCw/8d642a09-8bcf-427e-5509-e523c2140e00/public"
					alt="Alarm clock"
					class="w-48"
				/>
			</div>
			<h3 class="text-xl font-medium text-indigo-800">Your biological clock</h3>
		</div>

		<div
			class="flex flex-col justify-center items-center rounded-lg bg-white shadow-md hover:shadow-xl active:shadow-md transition-shadow 
			border-stone-200 p-8 space-y-8"
			in:fly={{ y: 5, duration: 1000, delay: 2000 }}
		>
			<div>
				<img
					src="https://imagedelivery.net/4v3KB3Aeo_3sLg3kKoifCw/e022f310-0aec-4344-5303-fc6144e85b00/public"
					alt="Battery"
					class="w-48"
				/>
			</div>
			<h3 class="text-xl font-medium text-indigo-800">Your sleep pressure</h3>
		</div>
	</div>
	<p
		class="max-w-3xl text-center"
		in:fly={{ y: 5, duration: 1000, delay: 3000 }}
		out:fade={{ duration: 400 }}
	>
		To establish a new sleep schedule, we need to plan for both. <br />
		Select the one you would like to work on first.
	</p>
{/if}

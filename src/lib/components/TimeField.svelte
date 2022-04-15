<script>
	export let time = '00:00';
	export let placeholder = '00:00';

	export let timeArray = [0, 0, 0, 0];

	const timeValidRegex = /^([0-1]?[0-9]|2[0-3]):[0-5][0-9]$/;

	// TODO: Handle input internally. Stop exposing time.
	// 			 Emit an event with timeArray in event.details
	// 			 when input contains valid value.
	// TODO: Try https://github.com/simeydotme/svelte-range-slider-pips
</script>

<div class="flex flex-row space-x-4 mt-5">
	<input
		type="text"
		placeholder={placeholder.substring(0, 1)}
		id="goal-bedtime-hour-1"
		class="bg-transparent h-16 w-12 border-2 border-stone-200 rounded-lg flex items-center text-center text-3xl placeholder:text-stone-400"
		on:input={(e) => {
			if (isNaN(e.target.value)) {
				e.target.value = '';
			}
			if (e.target.value.length === 1) {
				const chars = Array.from(time);
				chars[0] = e.target.value;
				if (timeValidRegex.test(chars.join(''))) {
					timeArray[0] = parseInt(chars[0]);
					timeArray[1] = parseInt(chars[1]);
					timeArray[2] = parseInt(chars[3]);
					timeArray[3] = parseInt(chars[4]);
					time = chars.join('');
				} else {
					e.target.value = '';
				}
				document.getElementById('goal-bedtime-hour-2').focus();
			}
			if (e.target.value.length > 1) {
				e.target.value = e.target.value.slice(0, 1);
				const chars = Array.from(time);
				chars[0] = e.target.value;
				if (timeValidRegex.test(chars.join(''))) {
					timeArray[0] = parseInt(chars[0]);
					timeArray[1] = parseInt(chars[1]);
					timeArray[2] = parseInt(chars[3]);
					timeArray[3] = parseInt(chars[4]);
					time = chars.join('');
				} else {
					e.target.value = '';
				}
				document.getElementById('goal-bedtime-hour-2').focus();
			}
		}}
	/>
	<input
		type="text"
		placeholder={placeholder.substring(1, 2)}
		id="goal-bedtime-hour-2"
		class="bg-transparent h-16 w-12 border-2 border-stone-200 rounded-lg flex items-center text-center text-3xl placeholder:text-stone-400"
		on:input={(e) => {
			if (isNaN(e.target.value)) {
				e.target.value = '';
			}
			if (e.target.value.length === 1) {
				const chars = Array.from(time);
				chars[1] = e.target.value;
				if (timeValidRegex.test(chars.join(''))) {
					timeArray[0] = parseInt(chars[0]);
					timeArray[1] = parseInt(chars[1]);
					timeArray[2] = parseInt(chars[3]);
					timeArray[3] = parseInt(chars[4]);
					time = chars.join('');
				} else {
					e.target.value = '';
				}
				document.getElementById('goal-bedtime-minute-1').focus();
			}
			if (e.target.value.length > 1) {
				e.target.value = e.target.value.slice(0, 1);
				const chars = Array.from(time);
				chars[1] = e.target.value;
				if (timeValidRegex.test(chars.join(''))) {
					timeArray[0] = parseInt(chars[0]);
					timeArray[1] = parseInt(chars[1]);
					timeArray[2] = parseInt(chars[3]);
					timeArray[3] = parseInt(chars[4]);
					time = chars.join('');
				} else {
					e.target.value = '';
				}
				document.getElementById('goal-bedtime-minute-1').focus();
			}
		}}
	/>
	<p class="text-4xl my-2">:</p>
	<input
		type="text"
		placeholder={placeholder.substring(3, 4)}
		id="goal-bedtime-minute-1"
		class="bg-transparent h-16 w-12 border-2 border-stone-200 rounded-lg flex items-center text-center text-3xl placeholder:text-stone-400"
		on:input={(e) => {
			if (isNaN(e.target.value)) {
				e.target.value = '';
			}
			if (e.target.value.length === 1) {
				const chars = Array.from(time);
				chars[3] = e.target.value;
				if (timeValidRegex.test(chars.join(''))) {
					timeArray[0] = parseInt(chars[0]);
					timeArray[1] = parseInt(chars[1]);
					timeArray[2] = parseInt(chars[3]);
					timeArray[3] = parseInt(chars[4]);
					time = chars.join('');
				} else {
					e.target.value = '';
				}
				document.getElementById('goal-bedtime-minute-2').focus();
			}
			if (e.target.value.length > 1) {
				e.target.value = e.target.value.slice(0, 1);
				const chars = Array.from(time);
				chars[3] = e.target.value;
				if (timeValidRegex.test(chars.join(''))) {
					timeArray[0] = parseInt(chars[0]);
					timeArray[1] = parseInt(chars[1]);
					timeArray[2] = parseInt(chars[3]);
					timeArray[3] = parseInt(chars[4]);
					time = chars.join('');
				} else {
					e.target.value = '';
				}
				document.getElementById('goal-bedtime-minute-2').focus();
			}
		}}
	/>
	<input
		type="text"
		placeholder={placeholder.substring(4, 5)}
		id="goal-bedtime-minute-2"
		class="bg-transparent h-16 w-12 border-2 border-stone-200 rounded-lg flex items-center text-center text-3xl placeholder:text-stone-400"
		on:input={(e) => {
			if (isNaN(e.target.value)) {
				e.target.value = '';
			}
			if (e.target.value.length === 1) {
				const chars = Array.from(time);
				chars[4] = e.target.value;
				if (timeValidRegex.test(chars.join(''))) {
					timeArray[0] = parseInt(chars[0]);
					timeArray[1] = parseInt(chars[1]);
					timeArray[2] = parseInt(chars[3]);
					timeArray[3] = parseInt(chars[4]);
					time = chars.join('');
				} else {
					e.target.value = '';
				}
			}
			if (e.target.value.length > 1) {
				e.target.value = e.target.value.slice(0, 1);
				const chars = Array.from(time);
				chars[4] = e.target.value;
				if (timeValidRegex.test(chars.join(''))) {
					timeArray[0] = parseInt(chars[0]);
					timeArray[1] = parseInt(chars[1]);
					timeArray[2] = parseInt(chars[3]);
					timeArray[3] = parseInt(chars[4]);
					time = chars.join('');
				} else {
					e.target.value = '';
				}
			}
		}}
	/>
</div>

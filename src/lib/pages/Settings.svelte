<script>
	import settings from '../stores/settings';
</script>

<h2>Settings</h2>

<button
	on:click={() => {
		$settings.colorScheme = $settings.colorScheme === 'dark' ? 'light' : 'dark';
	}}>Toggle Color Scheme</button
>

<!-- <label>
	<input bind:group={colorScheme} type="radio" name="colorScheme" value="dark" />
	Dark
</label>

<label>
	<input bind:group={colorScheme} type="radio" name="colorScheme" value="light" />
	Light
</label> -->

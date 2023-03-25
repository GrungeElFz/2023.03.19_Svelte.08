<script>
	import settings from '../stores/settings';

	let colorScheme;

	settings.subscribe((settings) => {
		colorScheme = settings.colorScheme;
	});

	$: {
		settings.update((prevSettings) => ({ ...prevSettings, colorScheme }));
	}
</script>

<h2>Settings</h2>

<label>
	<input bind:group={colorScheme} type="radio" name="colorScheme" value="dark" />
	Dark
</label>

<label>
	<input bind:group={colorScheme} type="radio" name="colorScheme" value="light" />
	Light
</label>

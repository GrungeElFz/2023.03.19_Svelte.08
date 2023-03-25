<script>
	import settings from '../stores/settings';

	let colorScheme;

	settings.subscribe((settings) => {
		colorScheme = settings.colorScheme;
	});
</script>

<h2>Home</h2>

{colorScheme}
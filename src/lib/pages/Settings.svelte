<script>
	import settings from '../stores/settings';
</script>

<h2>Settings</h2>

<label>
  <input bind:group={$settings.colorScheme} type="radio" name="colorScheme" value="dark" />
	Dark
</label>

<label>
  <input bind:group={$settings.colorScheme} type="radio" name="colorScheme" value="light" />
	Light
</label>

<br>

<button
on:click={() => {
  $settings.colorScheme = $settings.colorScheme === 'dark' ? 'light' : 'dark';
}}>Toggle Color Scheme</button
>

<p>Current Theme: {$settings.colorScheme}</p>

<script>
	import '../app.css';

	let { children } = $props();

	let theme = $state('dark');

	$effect(() => {
		theme = document.documentElement.dataset.theme === 'light' ? 'light' : 'dark';
	});

	function toggle() {
		theme = theme === 'dark' ? 'light' : 'dark';
		document.documentElement.dataset.theme = theme;
		try {
			localStorage.setItem('theme', theme);
		} catch {}
	}
</script>

<button class="theme-toggle" type="button" onclick={toggle} aria-label="Toggle color theme">
	{theme === 'dark' ? '☼ light' : '☾ dark'}
</button>

{@render children()}

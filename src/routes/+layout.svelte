<script>
	import '../app.css';
	let { children } = $props();
</script>
<svelte:head>
	<title>Ship It Interactive</title>
</svelte:head>

{@render children()}

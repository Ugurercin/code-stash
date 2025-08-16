<script lang="ts">
	import Sidebar from '$lib/components/Sidebar.svelte';

	let open = true;
	function handleToggle() {
		open = !open;
	}
</script>

<div class="flex min-h-screen bg-violet-950 text-neutral-200">
	<Sidebar {open} onToggle={handleToggle} />

	<main class="flex-1 p-8">
		<h1 class="text-3xl font-bold text-neutral-100">Welcome</h1>
		<p class="mt-2 text-neutral-400">Main content goes here</p>
	</main>
</div>
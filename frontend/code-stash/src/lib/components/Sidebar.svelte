<script lang="ts">
	import Button from '$lib/components/ui/button/button.svelte';
	import * as Tooltip from '$lib/components/ui/tooltip';
	import { Menu, X, Plus } from 'lucide-svelte';

	export let open = true;
	export let onToggle: () => void = () => {};
</script>

<aside
	class={`flex flex-col bg-neutral-950 border-r border-neutral-800 p-4 transition-all duration-300 ${
		open ? 'w-64' : 'w-16'
	}`}
>
	<div class={`flex items-center ${open ? 'justify-between' : 'justify-center'}`}>
		<Button onclick={onToggle} variant="ghost" size="icon" class="hover:bg-neutral-800">
			{#if open}
				<X class="h-5 w-5" />
			{:else}
				<Menu class="h-5 w-5" />
			{/if}
			<span class="sr-only">Toggle Menu</span>
		</Button>

		<Tooltip.Root delayDuration={200}>
			<Tooltip.Trigger>
				<Button
					variant="ghost"
					size="icon"
					class={`hover:bg-neutral-800 transition-opacity ${!open ? 'opacity-0 hidden' : 'opacity-100'}`}
				>
					<Plus class="h-5 w-5" />
					<span class="sr-only">New Snippet</span>
				</Button>
			</Tooltip.Trigger>

			<Tooltip.Content>
				<p>New Snippet</p>
			</Tooltip.Content>
		</Tooltip.Root>
	</div>

	<div class={`mt-6 transition-opacity duration-200 ${!open ? 'opacity-0' : 'opacity-100'}`}>
		<h1
			class={`text-xl font-bold bg-gradient-to-r from-purple-500 to-indigo-400 bg-clip-text text-transparent px-2 ${
				!open ? 'hidden' : ''
			}`}
		>
			CodeStash
		</h1>

		<ul class="mt-4 space-y-2">
			<li>
				<a
					href="/"
					class="flex items-center p-2 rounded-md bg-purple-950/50 border-l-2 border-purple-500 text-neutral-100"
				>
					Go API Server
				</a>
			</li>
			<li>
				<a
					href="/"
					class="flex items-center p-2 rounded-md text-neutral-400 hover:bg-neutral-900 hover:text-neutral-100 transition-colors"
				>
					Svelte Fetch Data
				</a>
			</li>
		</ul>
	</div>
</aside>
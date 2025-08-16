<script lang="ts">
	import '../app.css';
	import favicon from '$lib/assets/favicon.svg';
  
	// import Tooltip provider (use your path)
	import * as Tooltip from '$lib/components/ui/tooltip'; // or: import * as Tooltip from 'bits-ui';
  
	let { children } = $props();
  </script>
  
  <svelte:head>
	<link rel="icon" href={favicon} />
  </svelte:head>
  
  <Tooltip.Provider>
	{@render children?.()}
  </Tooltip.Provider>
  
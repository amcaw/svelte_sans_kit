<script>
import Fa from 'svelte-fa'
import { faBolt, faFire } from '@fortawesome/free-solid-svg-icons'

import { csv } from 'd3-fetch';

import { onMount } from 'svelte';

let datapoints = [];
	onMount(() => {
		csv("https://raw.githubusercontent.com/amcaw/energizor/main/BE_day.csv")
			.then((res) => {
			datapoints = res;
		})
	})

  
  $: ajd = datapoints.slice(-2, -1)
  
  
  </script>

{#each datapoints as datapoints}
<p>{datapoints.Value}</p>

{/each}



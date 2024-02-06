<script>
  // import { getContext } from 'svelte'
  import Outer from '$lib/snippets/Outer.svelte'
  // const outerContext = getContext('outerContext')
</script>

<h1>Inner - Outer</h1>
outerContext: 
<Outer>
{#snippet header(prop)}
hi from outer header
prop: {prop}
{/snippet}

Children content in Outer component


</Outer>
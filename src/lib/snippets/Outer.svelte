<script>
  // import { setContext } from 'svelte';
  let { children, header } = $props()
  let outerProp = 'outer prop'
  import Inner from './Inner.svelte'

  // setContext('outerContext', "Outer context");
</script>

<h2>Outer component</h2>

{#if header}
  <div>
  Rendering header 
    {@render header(outerProp)}
  </div>
{/if}



<Inner>
Hi Inner child content
{#snippet header(prop)}
<div>Children content in Inner inside Outer component</div>
{prop}
{/snippet}
</Inner>

{#if children}
<div>
Children not able to send prop.
  {@render children()}
</div>
{/if}
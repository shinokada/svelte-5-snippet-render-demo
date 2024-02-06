<script>
  let { children, header } = $props()
  let innerProp = 'inner prop'
  let headerProp = 'header prop'
</script>
<h3>Inner component</h3>


<div>
{#if header}
  {@render header(headerProp)}
{/if}
</div>
<div>
{#if children}
  {@render children(innerProp)}
{/if}
</div>
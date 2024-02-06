<script>
	import Compo1 from '$lib/Compo1.svelte';
  import Outer from '$lib/snippets/Outer.svelte'
  let mypageProp = 'my page prop'
</script>

<div style="background-color:gray; padding:8px;">
  <h1>Snippet and render</h1>

  <Compo1>

  <div style="background-color:pink; padding:8px;">
    Compo1 children content
  </div>

  <div>
  before snippet
  {#snippet header(prop)}
    My content prop: {prop}
  {/snippet}
  
  Page content bla bla: 
  </div>
  </Compo1>

  
</div>

<Outer>
{#snippet header(prop)}
hi from outer header
prop: {prop}
{/snippet}

Children content in Outer component


</Outer>
<script>
	let { children, header, ...props } = $props();
	import Compo2 from './Compo2.svelte'
  let compo1prop = 'compo1 prop'
  let isOpen = $state(false)
  const toggle = () => isOpen = !isOpen
</script>

<div style="background-color:red; padding:8px;">
<h1>Compo1</h1>
<button onclick={toggle}>
  Toggle button in Compo1
</button>

<div style="padding: 8px; margin: 8px;">
isOpen value in Compo1: <span style="background-color: blue; color:white;">{isOpen}</span>
</div>
  {#if header}
    <div>
      Rendering header 
      {@render header(compo1prop)}
  </div>
  {/if}

<Compo2 {isOpen}>
  <h2>Compo 1 header: This will come after</h2>
  {#snippet header(prop)}
  <h3>header in Compo1 > Compo2: sending prop </h3>
  <p>The prop will be the same as Compo2 header props, foo: "foo", bar: "bar"</p>
    {prop.foo}: {prop.bar}
  {/snippet}

<div style="background-color:green; padding: 8px">
Compo2 children content in Compo1
</div>

  {#snippet footer(prop)}
  <h3>header in Compo1 > Compo2 </h3>
  <p>The prop will be the same as Compo2 header props, baz: "baz",	qux: "qux"</p>
    {prop.baz}: {prop.qux}
  {/snippet}
</Compo2>


  {#if children}
  <div style="background-color: purple; padding:8px;">
    <h2>Compo 1 children</h2>
      {@render children()}
    </div>
  {/if}

</div>
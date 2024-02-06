<script>
	let { children, header, footer, isOpen } = $props();
  let headerProps = {
    foo: "foo",
    bar: "bar"
  }
	let footerProps = {
		baz: "baz",
		qux: "qux"
	}
  let childrenProps = {
    hoge: "hoge",
    corge: "corge"
  }

</script>

<div style="background-color: yellow; padding:8px;">
  <h1>Compo2 is Compo1's child component</h1>
  <div style="padding: 8px; margin: 8px;">
  isOpen value in Compo2: <span style="background-color: blue; color:white;">{isOpen}</span>
  </div>

    
  {#if header}
  <div>
    <h2>Compo2 header</h2>
      <h3>header in Compo 2: sending headerProps</h3>
      {@render header(headerProps)}
  </div>
  {/if}

  
  {#if children}
  <div style="background-color: purple; padding:8px;">
    <h2>Compo 2 children: sending compProps</h2>
      {@render children(childrenProps)}
    </div>
  {/if}
  

  {#if footer}
  <div>
    <h2>Compo 2 footer</h2>
      {@render footer(footerProps)}
    </div>
  {/if}
</div>
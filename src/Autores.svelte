<script>
  import { onMount, getContext } from "svelte";
  import { jsonData }            from "./store.js";

  import Buscar                  from "./Buscar.svelte";
  import Autor                from "./Autor.svelte";
  import Boton                   from "./Boton.svelte";

  const URL = getContext("URL");

  let busqueda = "";
  let autor = {};

  onMount(async () => {
    const response = await fetch(URL.autores);
    const data = await response.json();
    $jsonData = data;
  });

  $: regex = new RegExp(busqueda, "i");
  $: datos = busqueda 
    ? $jsonData.filter(item => regex.test(item.nombre))
    : $jsonData;

</script>

<style>
  .container {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: left;
    flex-wrap: wrap;
    padding: 15px 0px;
  }
</style>

<h1>Autores</h1>

<Buscar bind:busqueda />

<div class="container">
  <Autor bind:autor>
    <div style="text-align: right">
      <Boton documento={autor} tipo="insertar" coleccion="articulos" />
    </div>
  </Autor>
</div>
<div class="container">
  {#each datos as autor}
    <Autor {autor}>
      <div style="text-align: right">
        <Boton documento={autor} tipo="modificar" coleccion="articulos" />
        <Boton documento={autor} tipo="eliminar"  coleccion="articulos" />
      </div>
    </Autor>
  {/each}
</div>

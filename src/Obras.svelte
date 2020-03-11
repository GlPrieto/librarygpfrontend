<script>
  import { onMount, getContext } from "svelte";
  import { jsonData }            from "./store.js";

  import Buscar                  from "./Buscar.svelte";
  import Obra                from "./Obra.svelte";
  import Boton                   from "./Boton.svelte";
  
  const URL = getContext("URL");

  let busqueda = "";
  let obra = {};

  onMount(async () => {
    const response = await fetch(URL.obras);
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
  }
</style>

<h1>Obras</h1>

<Buscar bind:busqueda />

<div class="container">
  <Obra bind:obra>
    <div style="text-align: right">
      <Boton documento={obra} tipo="insertar" coleccion="obras" />
    </div>
  </Obra>
</div>
<div class="container">
  {#each datos as obra}
    <Obra {obra}>
      <div style="text-align: right">
        <Boton documento={obra} tipo="modificar" coleccion="obras" />
        <Boton documento={obra} tipo="eliminar"  coleccion="obras" />
      </div>
    </Obra>
  {/each}
</div>

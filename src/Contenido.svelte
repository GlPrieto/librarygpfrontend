<script>
  import { Route }  from "svelte-routing";
  import Inicio     from "./Inicio.svelte";
  import Autores  from "./Autores.svelte";
  import Obras   from "./Obras.svelte";
</script>

<style>
  main {
    padding: 20px;
    padding-top: 50px;
  }
</style>

<main id="contenido">
  <Route path="/" component={Inicio} />
  <Route path="/autores" component={Autores} />
  <Route path="/obras" component={Obras} />
</main>

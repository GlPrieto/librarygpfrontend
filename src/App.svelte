<script>
  import { setContext } from "svelte";
  import { Router } from "svelte-routing";
  import { writable } from "svelte/store";
  import Contenido from "./Contenido.svelte";
  import Nav from "./Nav.svelte";

  const URL = {
    autores: " https://librarygpbackend.herokuapp.com/api/autores/",
    obras:  " https://librarygpbackend.herokuapp.com/api/obras/"
  };

  setContext("URL", URL);
</script>

<style>
  :global(.inversed) {
    filter: brightness(0) invert(1);
  }

  :global(.nav-link a){
    color: white;
  }

  :global(.nav-link a:hover){
    color: lightgray;
  }
</style>

<Router>
  <Nav />
  <Contenido />
</Router>

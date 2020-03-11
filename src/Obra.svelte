<script>
  import Boton from "./Boton.svelte";

  export let obra = {};
</script>

<style>
  .title {
    font-weight: bold;
  }
  .card {
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    border-radius: 5px;
    transition: 0.3s;
    padding: 10px;
    margin: 10px;
  }

  .card:hover {
    box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.4);
  }

  input {
    background-color: rgba(252, 252, 252, 0.925);
    padding: 10px;
    font-size: 14px;
    color: black;
    border: 0.5 gray;
    outline: none;
    margin-left: 5px;
    margin-bottom: 5px;
  }
    input:focus {
    background-color: rgb(179, 230, 245);
  }

  input:required:invalid,
  input:focus:invalid {
    background-color: rgb(255, 182, 182);
  }
</style>


  <div class="card" on:click>
    <input bind:value={obra.nombre} class="title" />
    <input bind:value={obra.genero} class="title" />
    <slot />
  </div>


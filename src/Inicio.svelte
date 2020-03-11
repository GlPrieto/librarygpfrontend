<script>
  import { Link } from "svelte-routing";
</script>

<style>
  h1,
  div,
  p {
    padding: 3px;
  }
  div {
    padding: 30px;
  }

  .bloque {
    display: flex;
    flex-direction: column;
  }
  .resumen {
    display: flex;
    flex-wrap: wrap;    
    padding: 5px;
    margin: 0 0 15px;
    border: 1px solid #000;
    border-radius: 4px;
    box-shadow: 0 0 3px rgba(0, 0, 0, 0.19);
    border: 1px solid rgb(34, 57, 88);
    border-radius: 4px;
  }

  .opcion {
    display: flex;   
    word-break: break-word;
    padding: 0 10px;
    font-size: 14px;
    font-weight: 700;
    text-shadow: 0 1px 0 rgba(0, 0, 0, 0.1);
    font-family: sans-serif;
    color: #3b4151;
    border-radius: 4px;
    background: #c9defd;
    min-width: 140px;
    padding: 10px;
  }

  .descripcion {
    font-size: 14px;
    flex: 1 1 auto;
    word-break: break-word;
    font-family: sans-serif;
    color: #3b4151;
    padding-top: 10px;
    padding-left: 10px;
  }
</style>

<h1>Biblioteca GP</h1>
<p>
  <small>
    <b>Progressive Web App (PWA)</b>
  </small>
</p>
<p>
  <small>
    Backend en
    <a href="https://librarygpbackend.herokuapp.com/">
      https://librarygpbackend.herokuapp.com/
    </a>
  </small>
</p>
<p>Contenido de la base de datos</p>

<div class="bloque">
  <Link to="/">
    <div class="resumen">
      <span class="opcion">Inicio</span>
      <span class="descripcion">Esta página de información.</span>
    </div>
  </Link>

  <Link to="/autores">
    <div class="resumen">
      <span class="opcion">Autores</span>
      <span class="descripcion">
        Operaciones CRUD de artículos en una BD.
      </span>
    </div>
  </Link>

  <Link to="/obras">
    <div class="resumen">
      <span class="opcion">Obras</span>
      <span class="descripcion">
        Operaciones CRUD de clientes en una BD.
      </span>
    </div>
  </Link>

</div>
  <p>
  <small>
    <b>
      Código fuente de la aplicación de ejemplo en
      <a href="https://github.com/jamj2000/tiendafrontend">
        https://github.com/jamj2000/tiendafrontend
      </a>
    </b>
  </small>
</p>
  <p>
  <small>
    <b>
      Código fuente de DevPC en
      <a href="https://github.com/Kibrands/devpc">
        https://github.com/Kibrands/devpc
      </a>
    </b>
  </small>
</p>
  <p>
  <small>
    <b>
      Código fuente de esta aplicación en
      <a href="https://github.com/GlPrieto/librarygpfrontend">
        https://github.com/GlPrieto/librarygpfrontend
      </a>
    </b>
  </small>
</p>

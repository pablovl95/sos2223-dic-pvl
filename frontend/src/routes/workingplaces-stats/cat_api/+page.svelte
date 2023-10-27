<script>
  let imagen = '';

  async function fetchCatImage() {
    try {
      const response = await fetch('https://api.thecatapi.com/v1/images/search');
      const data = await response.json();
      imagen = data[0].url;
    } catch (error) {
      console.error(error);
    }
  }
</script>

<main>
  <h1>Fotos de Gatos</h1>
  <button on:click={fetchCatImage}>Mostrar Foto Aleatoria</button>
  {#if imagen}
    <img src="{imagen}" class="cat-image" />
  {/if}
</main>

<style>
  main {
    text-align: center;
    margin: 20px;
  }

  button {
    padding: 10px 20px;
    font-size: 16px;
  }

  img {
    max-width: 100%;
    border: 1px solid #ccc;
    border-radius: 5px;
  }
</style>

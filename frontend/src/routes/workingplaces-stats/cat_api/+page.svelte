<script>
  let catImage = '';

  async function fetchCatImage() {
    const response = await fetch('https://thecatapi.com/api/images/get?format=src&type=jpg');
    catImage = response.url;
  }
</script>

<main>
  <h1>Fotos de Gatos</h1>
  <button on:click={fetchCatImage}>Mostrar Otra Foto</button>
  {#if catImage}
    <img src={catImage} alt="Gato" />
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

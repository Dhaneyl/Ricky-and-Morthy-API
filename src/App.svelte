<!-- Javascript syntax -->
<script>
  import Character from "./lib/Character.svelte";
  // local vars
  let page = 3;
  let characters = [];
  // Fetchin the api
  const loadCharacters = async () => {
    const response = await fetch(
      `https://rickandmortyapi.com/api/character?page=${page}`
    );
    const data = await response.json();
    console.log(data);
    characters = data.results;
  };

  loadCharacters();
  // Buttons logic
  const nextPage = () => {
    page++;
    loadCharacters();
  };
  const previustPage = () => {
    page--;
    loadCharacters();
  };
</script>

<!-- Html code -->
<main>
  <h1 class="title">Rick & Morthy</h1>
  <div class="container">
    <div class="btns" >
      <button on:click={previustPage} disabled={page === 1} class="btn">Previus</button>
      <button on:click={nextPage} disabled={page === 42} class="btn">Next</button>
    </div>
    <div class="grid">
      {#each characters as character}
      <Character character={character}/>
   {/each}
    </div>  
  </div>
</main>

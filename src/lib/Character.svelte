<!-- Js syntax -->
<script>
  // This is the way we can manage props in svelte
  export let character;
</script>

<!-- Html code -->
<div class="character">
  
  <img src={character.image} alt="character.name" />
  <h1>{character.name}</h1>
  <p> <span class="span">Location:</span> {character.location.name}</p>
  <p><span class="span">Origin: </span> {character.origin.name}</p>
</div>

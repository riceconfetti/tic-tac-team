<script>
  import Square from "./Square.svelte";
  import icons from "../assets/characters.json";

  export let size;
  let squares = [];
  export let colors;

  //console.log(icons);

  function getRandomInt(min, max) {
    min = Math.ceil(min);
    max = Math.floor(max);
    return Math.floor(Math.random() * (max - min) + min); // The maximum is exclusive and the minimum is inclusive
  }
  
  const range = icons.length;
  let random;

  function getNewCharacter() {
    random = getRandomInt(0, range - 1);
    //console.log( icons[random].name);
    squares.forEach((square) => {
      if (icons[random] == square) {
        getNewCharacter();
      }
    });
    return icons[random];
  }

  for (let i = 0; i < size * size; i++) {
    let character = getNewCharacter();
    //console.log(character);
    squares.push(character);
  }
</script>

<div class="board" style="--board_size: {size}">
  {#each squares as square, i}
    <Square {colors} value={square} />
  {/each}
</div>

<style>
  :global(.board) {
    display: grid;
    grid-template-columns: repeat(var(--board_size), auto);
    width: auto;
    margin-top: 16px;
  }
</style>

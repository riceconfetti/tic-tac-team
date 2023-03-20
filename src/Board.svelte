<script>
  import Square from "./Square.svelte";
  import { icons } from "./characters.js";

  let size = 5;
  let squares = [];

  console.log(icons);

  function getRandomInt(min, max) {
    min = Math.ceil(min);
    max = Math.floor(max);
    return Math.floor(Math.random() * (max - min) + min); // The maximum is exclusive and the minimum is inclusive
  }
  
  const range = icons.length;
  let random;

  function getNewCharacter() {
    random = getRandomInt(0, range - 1);
    squares.forEach((square) => {
      if (icons[random] == square) {
        getNewCharacter();
      }
    });
    return icons[random];
  }

  for (let i = 0; i < size * size; i++) {
    let character = getNewCharacter();
    console.log(character);
    squares.push(character);
  }
</script>

<div class="board" style="--board_size: {size}">
  {#each squares as square, i}
    <Square value={square} />
  {/each}
</div>

<style>
  .board {
    display: grid;
    grid-template-columns: repeat(var(--board_size), auto);
    width: auto;
  }
</style>

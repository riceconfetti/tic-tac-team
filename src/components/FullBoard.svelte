<script>
  import Square from "./Square.svelte";
  import icons from "../assets/characters.json";

  export let colors;
  let size = 7;
</script>

<div class="board" style="--board_size: {size}">
  {#each icons as square, i}
    <Square {colors} value={square} />
  {/each}
</div>

<style>
  .board {
    display: flex;
    width: 100%;
    flex-wrap: wrap;
    justify-content: center;
  }
</style>


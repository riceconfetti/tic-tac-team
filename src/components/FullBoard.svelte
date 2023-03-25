<script>
  import Square from "./Square.svelte";
  import { icons } from "../assets/characters.js";

  export let colors;
  let size = 7;
</script>

<div class="board" style="--board_size: {size}">
  {#each icons as square, i}
    <Square {colors} value={square} />
  {/each}
</div>


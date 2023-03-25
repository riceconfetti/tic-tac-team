<script>
   import { Link } from "svelte-routing";
</script>

<Link class="link" to="/board-4">4x4</Link>
<Link class="link" to="/board-5">5x5</Link>
<Link class="link" to="/board-6">6x6</Link>
<Link class="link" to="/board-full">full</Link>

<style>
  :global(.link) {
     padding: 10px 20px;
     background-color: rgb(70, 70, 119);
     border-radius: 20px;
     color: white;
     font-weight: bold;
     text-transform: uppercase;
     letter-spacing: 1px;
  }
</style>

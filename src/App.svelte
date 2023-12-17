<script>
  import Board from "./components/Board.svelte";
  import FullBoard from "./components/FullBoard.svelte";
  import Nav from "./components/Nav.svelte";
  import Home from "./pages/Home.svelte";
  import { Router, Route } from "svelte-routing";
  
  const title = "Tic Tac Team";
  const og_colors = ['#b0d3f1', '#b1ec9a', '#efb5bd ', '#f3daa4 ', '#35d0f4', '#888'];
  
</script>

<svelte:head>
  <title>{title}</title>
</svelte:head>

<h1>{title}</h1>

<Router>
  <Route path="/" component={Home}/>
  <Route path="/board-4">
    <Nav />
    <Board size="4" colors={og_colors}/>
  </Route>
  <Route path="/board-5">
    <Nav />
    <Board size="5" colors={og_colors}/>
  </Route>
  <Route path="/board-6">
    <Nav />
    <Board size="6" colors={og_colors}/>
  </Route>
  <Route path="/board-full">
    <Nav />
    <FullBoard colors = {og_colors}/>
  </Route>
</Router>

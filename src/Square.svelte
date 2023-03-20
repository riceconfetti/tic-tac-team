<script>
    export let value;
    let colors = ['#b0d3f1', '#b1ec9a', '#efb5bd ', '#f3daa4 ', '#35d0f4', '#888'];
    let index = 0;
    
    function handleClick() {
      if (index < 5 ){ 
        index += 1;
      } else {
        index = 0;
      }
      console.log(index);
    }
  </script>
  
  <style>
    .square {
      width: 90px;
      height: 90px;
      background-color: whitesmoke;
      margin: 5px;
      padding: 5px;
      font-size: 20px;
      text-align: center;
    }

    .square img {
        width:100%;
        height: 100%;
    }
  
    .square:hover {
      border: 2px solid grey;
    }

    .dead img {
      filter: grayscale(1);
    }
  </style>
  
  <button on:click={handleClick} class="square" class:dead="{index===5}" style:background-color={colors[index]}><img src="{value.url}" alt="{value.name}"/></button>
  
  
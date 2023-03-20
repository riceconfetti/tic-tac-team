<script>
    export let value;
    let colors = ['#5B5F97', '#FFC145', '#FF6B6C ', '#2EC4B6 ', '#D3C4E3', 'grey'];
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
      border: 2px solid black;
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
  
  
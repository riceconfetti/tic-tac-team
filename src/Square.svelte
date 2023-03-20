<script>
    export let value;
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
      border: 2px solid red;
    }
  </style>
  
  <button class="square"><img src="{value.url}" alt="{value.name}"/></button>
  
  
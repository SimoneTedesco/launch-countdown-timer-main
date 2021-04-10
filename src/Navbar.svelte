<script>
  let inputValue = "prova"
  const handleInput = ({target}) => {
    inputValue = target.value
  }
  
</script>

<nav class="navbar">
  <h1>player scoreboard {inputValue}</h1>
  <!-- one way binding -->
  <!-- <input type="text" on:input={handleInput}> -->
  
  <!-- two way binding + shorthand -->
  <input type="text" bind:value={inputValue}>
</nav>

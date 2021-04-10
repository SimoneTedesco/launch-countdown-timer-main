<script>
  let inputValue = "prova"
  const handleInput = ({target}) => {
    inputValue = target.value
  }
  
</script>

<nav class="navbar">
  <h1>player scoreboard {inputValue}</h1>
  <input type="text" on:input={handleInput}>
</nav>

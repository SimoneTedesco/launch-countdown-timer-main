<script>
  let inputValue = "prova"
  const handleInput = ({target}) => {
    inputValue = target.value
  }
  
  // scrivendo così il valore non si aggiorna;
  let reactiveValue = inputValue;
  // invece così il valore si aggiorna, è una specie di watcher
  $: reactiveValue = inputValue

  // questo per fare piu cose contemporaneamente
  $: {
    console.log('reactiveValue :>> ', reactiveValue);
    console.log('reactiveValue :>> ', reactiveValue);
  }
  
</script>

<nav class="navbar">
  <h1>player scoreboard {inputValue}</h1>
  <p>{reactiveValue}</p>
  <!-- one way binding -->
  <!-- <input type="text" on:input={handleInput}> -->
  
  <!-- two way binding + shorthand -->
  <input type="text" bind:value={inputValue}>
</nav>

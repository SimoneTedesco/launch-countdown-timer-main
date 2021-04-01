<script>
  let name = "prova";
  let points = 100;
  let showControls = false;

  const addPoint = () => (points += 1);
  const removePoint = () => (points -= 1);
  const toggleControls = () => (showControls = !showControls);
</script>

<main>
  <h1>Hello {name}!</h1>
  <h2>Points: {points}</h2>
  <div>
    <button on:click={toggleControls}
      >{showControls ? "hide" : "show"} something</button
    >
  </div>
  {#if showControls}
    <button on:click={addPoint}> +1 </button>
    <button on:click={removePoint}> -1 </button>
    <input type="number" bind:value={points} />
  {/if}
  <p>
    Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn
    how to build Svelte apps.
  </p>
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

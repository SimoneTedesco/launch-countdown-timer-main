<script>
  export let name;
  export let points;
  let showControls = false;

  const addPoint = () => (points += 1);
  const removePoint = () => (points -= 1);
  const toggleControls = () => (showControls = !showControls);
</script>

<div class="card">
  <h1>{name}!</h1>
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
</div>

<style>
  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }
</style>

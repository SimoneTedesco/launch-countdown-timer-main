<script>
  export let name;
  export let points;
  export let index;
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  let showControls = false;
  const addPoint = () => (points += 1);
  const removePoint = () => (points -= 1);
  const toggleControls = () => (showControls = !showControls);
  const deletePlayer = () => dispatch("removeplayer", index);
</script>

<div class="card">
  <h1>{name}!</h1>
  <h2>Points: {points}</h2>
  <div>
    <button on:click={toggleControls}
      >{showControls ? "hide" : "show"} something</button
    >
    <button on:click={deletePlayer}> DELETE </button>
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

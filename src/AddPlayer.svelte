<script>
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();
  const defaultPlayer = {
    name: "",
    points: 0,
  };
  let player = { ...defaultPlayer };
  const onSubmit = (e) => {
    e.preventDefault();
    dispatch("addplayer", player);
    player = defaultPlayer;
  };
</script>

<form class="grid-3" on:submit={onSubmit}>
  <input type="text" placeholder="Player Name" bind:value={player.name} />
  <input type="number" placeholder="Player points" bind:value={player.points} />
  <input type="submit" value="Add Player" />
</form>

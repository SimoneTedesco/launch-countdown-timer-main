<script>
  import Navbar from "./Navbar.svelte";
  import Player from "./Player.svelte";
  import AddPlayer from "./AddPlayer.svelte";

  let players = [
    {
      name: "asd",
      points: 12,
    },
    {
      name: "asdasd",
      points: 22,
    },
    {
      name: "asdasdasd",
      points: 32,
    },
  ];

  const addPlayer = (e) => {
    const newPlayer = e.detail;
    players = [...players, newPlayer];
  };
</script>

<Navbar />
<main>
  <AddPlayer on:addplayer={addPlayer} />
  {#if players.length === 0}
    <p>No players</p>
  {:else}
    {#each players as { name, points }}
      <Player {name} {points} />
    {/each}
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

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

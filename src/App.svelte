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

  const removePlayer = (e) => {
    const index = e.detail;
    players = players.filter((x, i) => i !== index);
  };
</script>

<Navbar />
<main>
  <AddPlayer on:addplayer={addPlayer} />
  {#if players.length === 0}
    <p>No players</p>
  {:else}
    {#each players as { name, points }, index}
      <Player {name} {points} {index} on:removeplayer={removePlayer} />
    {/each}
  {/if}
  <!-- https://svelte.dev/tutorial/basics -->
  <!-- https://www.youtube.com/watch?v=zojEMeQGGHs&list=PL4cUxeGkcC9hlbrVO_2QFVqVPhlZmz7tO&index=1 -->
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

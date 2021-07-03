<script>
  import Navbar from "./Navbar.svelte";
  import Player from "./Player.svelte";
  import AddPlayer from "./AddPlayer.svelte";
  import Modal from "./Modal.svelte";
  let showModal = false
  let players = [
    {
      name: "asd",
      points: 12,
      id: 1,
    },
    {
      name: "asdasd",
      points: 22,
      id: 2,
    },
    {
      name: "asdasdasd",
      points: 32,
      id: 3,
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

  const toggleModal = () => {
    showModal = !showModal
  }
</script>

<Navbar />
<main>
  <!-- |once è un event modifier che rende apribile la modale solo una volta -->
  <button on:click|once={toggleModal}>open modal</button>
  <!-- onclick è forwardato -->
  <Modal {showModal} on:click={toggleModal}>
    <h3>wowo owow</h3>
    <form>
      <input type="text" placeholder="1111">
      <input type="text" placeholder="2222">
      <button>add person</button>
    </form>
    <div slot="title">
      <h3>Add a new person</h3>
    </div>
  </Modal>
  {#if players.length !== 5}
    <AddPlayer on:addplayer={addPlayer} />
  {/if}
  <!-- metodo classico con if -->
  <!-- {#if players.length === 0}
    <p>No players</p>
  {:else}
    {#each players as { name, points, id }, index (id)}
      <Player {name} {points} {index} on:removeplayer={removePlayer} />
    {/each}
  {/if} -->

  <!-- metodo WOW -->
  {#each players as { name, points, id }, index (id)}
    <Player {name} {points} {index} on:removeplayer={removePlayer} />
  {:else}
    <p>No players</p>
  {/each}
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

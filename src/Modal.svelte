<script>
  // uso export per variabili che arrivano dall'esterno
  // export let msg = "default msg";
  export let showModal = false;
  let isPromo = true;
</script>

<style>
  .backdrop {
    width: 100%;
    height: 100%;
    position: fixed;
    background-color: rgba(0, 0, 0, 0.8);
  }
  .modal {
    padding: 10px;
    border-radius: 10px;
    max-width: 400px;
    margin: 10% auto;
    text-align: center;
    background-color: white;
    color: #000;
  }
  .promo {
    background-color: crimson;
    color:white;
  }
</style>

{#if showModal}
<!-- on:click a vuoto inoltra l'evento al componente parent-->
<!-- aggiungendo "|self" si aggiunge un modifier dell'evento che in questo caso rende cliccabile solo l'elemento con onclick e non i figli -->
<div class="backdrop" on:click|self>
  <!-- class:promo aggiunge la classe "promo" condizionalmente -->
  <div class="modal" class:promo={isPromo}>
    <!-- tag speciale che renderizza i children del componente -->
    <slot></slot>
  </div>
</div>
{/if}

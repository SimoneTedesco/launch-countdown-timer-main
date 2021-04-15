<script>
  // uso export per variabili che arrivano dall'esterno
  export let msg = "default msg";
  let showModal = true;
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
<!-- class:promo aggiunge la classe "promo" condizionalmente -->
<div class="backdrop">
  <div class="modal" class:promo={isPromo}>
    <p>{msg || "asdasd"} </p>
  </div>
</div>
{/if}

<script>
  let name;
  let beltColor;
  let age;

  const handleSubmit = () => {
    console.log('name :>> ', name);
    console.log('beltColor :>> ', beltColor);
    console.log('age :>> ', age);
  }
</script>

<form on:submit|preventDefault={handleSubmit}>
  <input type="text" placeholder="1111" bind:value={name}>
  <input type="text" placeholder="2222" bind:value={beltColor}>
  <!-- svelte traduce in automatico input number in numero -->
  <input type="number" placeholder="age" bind:value={age}/>
  <button>add person</button>
</form>


<style></style>
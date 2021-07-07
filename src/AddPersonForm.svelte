<script>
  let name;
  let beltColor;
  let age;
  // let fighting = false;
  // let sneaking = false;
  // let running = false;
  // let skills = [];

  const handleSubmit = () => {
    console.log('name :>> ', name);
    console.log('beltColor :>> ', beltColor);
    console.log('age :>> ', age);
    // console.log('fighting :>> ', fighting);
    // console.log('sneaking :>> ', sneaking);
    // console.log('running :>> ', running);
    // console.log('skills :>> ', skills);
  }
</script>

<form on:submit|preventDefault={handleSubmit}>
  <input type="text" placeholder="1111" bind:value={name}>
  <input type="text" placeholder="2222" bind:value={beltColor}>
  <!-- svelte traduce in automatico input number in numero -->
  <input type="number" placeholder="age" bind:value={age}/>
  <label for="">skills:</label>
  <!-- checkbox singoli -->
  <!-- <input type="checkbox" bind:checked={fighting}>fighting <br>
  <input type="checkbox" bind:checked={sneaking}>sneaking <br>
  <input type="checkbox" bind:checked={running}>running <br> -->
  <!-- checkbox multipli -->
  <!-- <input type="checkbox" bind:group={skills} value={"fighting"}>fighting <br>
  <input type="checkbox" bind:group={skills} value={"sneaking"}>sneaking <br>
  <input type="checkbox" bind:group={skills} value={"running"}>running <br> -->
  <button>add person</button>
</form>


<style></style>
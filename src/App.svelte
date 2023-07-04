<script>
  import AppButton from "./components/AppButton.svelte";
  import Countries from "./components/Countries.svelte";
  import MemeEvent from "./components/MemeEvent.svelte";

  const appName = 'App';
  const imgSrc = 'https://via.placeholder.com/150';
  let inputValue = 'thing';

  let firstName = 'Meme';
  let lastName = 'Man';
  let count = 0;
  $: fullName = firstName + " " + lastName;

  function updateFirstName() {
    firstName = 'Bruh';
  }

  function incrementCount() {
    count += 1;
  }

  function handleMeme() {
    console.log('handle the meme');
  }
</script>

<main>
  <Countries />
  <MemeEvent on:meme={handleMeme} />

  <div class="container">
    <AppButton on:click={incrementCount}></AppButton>

    <p>The count is {count}</p>
    <img src={imgSrc} alt="">
  </div>
  
  <p>you name is {fullName}</p>

  <button on:click={updateFirstName}>Update name</button>
  <div class="input-container">
    <label for="input_thing">Enter a thing</label>
    <input type="text" id="input_thing" bind:value={inputValue}>
    <h2>This be input binding: {inputValue}</h2>
  </div>
</main>

<style>
  .container {
    display: flex;
    flex-direction: column;
    width: 200px;
    margin: 24px 0;
  }

  img {
    width: 150px;
    height: 150px;
    margin-top: 12px;
  }
</style>

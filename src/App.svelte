<script>
  import AppButton from "./components/AppButton.svelte";
  import Countries from "./components/Countries.svelte";

  const appName = 'App';
  const imgSrc = 'https://via.placeholder.com/150';

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
</script>

<main>
  <Countries />


  <div class="container">
    <AppButton on:click={incrementCount}></AppButton>
    
    <p>The count is {count}</p>
    <img src={imgSrc} alt="">
  </div>
  
  <p>you name is {fullName}</p>

  <button on:click={updateFirstName}>Update name</button>
</main>

<style>
  .container {
    display: flex;
    flex-direction: column;
    width: 200px;
  }

  img {
    width: 150px;
    height: 150px;
    margin-top: 12px;
  }
</style>

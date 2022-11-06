<script>
  const data = getCountries();

  async function getCountries() {
    const res = await fetch('https://restcountries.com/v3.1/all');
    const data = await res.json();

    // Just want first 10 for now
    return data.slice(0, 10);
  }

</script>

{#await data}
  <p>waiting...</p>
{:then countries}
  {#each countries as country}
    <p>{country.name.common}</p>
  {/each}
{:catch error}
  <p>An error occured</p>
{/await}

<style></style>
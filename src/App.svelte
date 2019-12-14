<script>
  import Header from "./Header.svelte";
  import InputForm from "./InputForm.svelte";

  let love;
  let loading = false

  function handleLove({ detail: loveJson }) {
    love = loveJson;
    console.log(love);
  }
</script>

<Header />
<InputForm on:data={handleLove} />
{#if love}
<h1 class="text-2xl md:text-6xl text-red-700 font-mono text-center">
	{love.percentage}
</h1>
<h3 class="md:text-3xl text-red-700 font-mono text-center">
	{love.result}
</h3>
{/if}

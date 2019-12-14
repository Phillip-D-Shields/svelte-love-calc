<script>
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();

  const apiBaseUrl = "https://love-calculator.p.rapidapi.com/getPercentage?";
  // fname=&sname=

  
  let loveJson, loverOne, loverTwo;

  async function onSubmit(e) {
    e.preventDefault();
    const res = await fetch(
      apiBaseUrl + "fname=" + loverOne + "&sname=" + loverTwo,
      {
        method: "GET",
        headers: {
          "x-rapidapi-host": "love-calculator.p.rapidapi.com",
          "x-rapidapi-key": "38fcf7fcfamshc75632e3ce098bdp1db136jsn816d2fbc625e"
        }
      }
    );
    loveJson = await res.json();
    
    dispatch('data', loveJson);
  };
</script>

<form
  on:submit={onSubmit}
  class="w-full text-red-700 px-4 text-center text-xl md:text-3xl">

  <div class="w-full py-8">
    <!-- first name input -->
    <div class="w-full md:w-1/2 mx-auto">
      <label for="lover one">First Lovers Name</label>
      <input
        type="text"
        bind:value={loverOne}
        placeholder="Lovuh One"
        class="appearance-none border-b-4 border-red-700" />
    </div>
    <!-- second name input -->
    <div class="w-full md:w-1/2 mx-auto">
      <label for="lover two">Second Lovers Name</label>
      <input
        type="text"
        bind:value={loverTwo}
        placeholder="Lovuh Two"
        class="appearance-none border-b-4 border-red-700" />
    </div>
  </div>
  <button type="submit" class="px-4 py-1 rounded-full bg-red-700 text-white">
    submit
  </button>

</form>

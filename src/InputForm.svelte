<script>

let loverOne, loverTwo;


const onSubmit = e => {
    e.preventDefault();
    console.log('submitted');
} 
</script>


<form on:submit={onSubmit} class="w-full text-red-700 px-4 text-center text-xl md:text-3xl">

<div class="w-full py-8">
    <!-- first name input -->
    <div class="w-full md:w-1/2 mx-auto">
        <label for="lover one">First Lovers Name </label>
        <input type="text" bind:value={loverOne} placeholder="Lovuh One" class="appearance-none border-b-4 border-red-700">
    </div>
    <!-- second name input -->
    <div class="w-full md:w-1/2 mx-auto">
        <label for="lover two">Second Lovers Name </label>
        <input type="text" bind:value={loverOne} placeholder="Lovuh Two" class="appearance-none border-b-4 border-red-700">
    </div>
</div>
<button type="submit" class="px-4 py-1 rounded-full bg-red-700 text-white">submit</button>

</form>
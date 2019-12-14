<script>
	import Header from './Header.svelte';
	import InputForm from './InputForm.svelte';

	function showLove() {
		
	}
</script>




<Header/>
<InputForm on:loveMeasured={showLove}/>
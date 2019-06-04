<script>

	import ContactCard from './ContactCard.svelte'

	let name = 'Andrew';
	let age = 32;

	$: uppercaseName = name.toUpperCase();
	$: console.log(name)
	$: if (name === 'Diana') {
		age = 30
	} 


	function incrementAge() {
		age += 1;
	}

	function changeName(){
		console.log('it runs')
		name = "Diana";
	}

	function nameInput(event) {
		const enteredvalue = event.target.value;
		name = enteredvalue;
	}


</script>

<style>
	h1 {
		color: purple;
	}
</style>

<h1>Hello {uppercaseName}, my age is {age}!</h1>
<button on:click="{incrementAge}">Change Age</button>
<button on:click={changeName}>Change Name</button>
<input type="text" value="{name}" on:input={nameInput}>
<input type="text" bind:value="{name}"  >

<ContactCard />



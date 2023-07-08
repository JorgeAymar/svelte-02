<script>
	let saludo ="Svelte Contador";
	let contador = 0;
	let textColor = 'text-primary'; 

	const aumentar = () => {
		contador ++;
	}

	$: doble = contador * 2;
	$: mensaje = contador > 5 ? 'Es mayor a 5' : 'Es menor o igual a 5'

	$: if (contador > 5){
			textColor = 'text-danger';
	}

</script>

<main>
	<h1> {saludo} </h1>
	<h2 class={textColor}>contador: {contador} </h2>
	<button on:click={aumentar}> Aumentar </button>
	<h2>{mensaje}</h2>

	<h2>Doble: {doble} </h2>
</main>

<style>

	.text-primary {
		color: blue;
	}

	.text-danger {
		color: red;
	}

	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>
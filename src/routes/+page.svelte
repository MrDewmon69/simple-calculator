<script lang="ts">
	let input = '';
	let result: any = 0;

	function calculate() {
		try {
			result = eval(input);
		} catch (error) {
			result = 'Error';
		}
		input = '';
	}
</script>

<svelte:head>
	<title>{result}</title>
</svelte:head>

<h1>
	{#if result > 1}
		{result}
	{/if}
	Welcome to my Calculator
</h1>
<p>Output: {input || result}</p>
{#if result == 69}
	<h1>NICE!!!!!!</h1>
{/if}
<div class="calc-body">
	<button on:click={() => (input += '/')}>/</button>
	<button on:click={() => (input += '5')}>5</button>
	<button on:click={() => (input += '9')}>9</button>
	<button on:click={() => (input += '0')}>0</button>
	<button on:click={() => (input += '+')}>+</button>
	<button on:click={() => (input += '6')}>6</button>
	<button on:click={() => (input += '2')}>2</button>
	<button on:click={() => (input += '8')}>8</button>
	<button on:click={() => (input += '.')}>.</button>
	<button on:click={() => (input += '4')}>4</button>
	<button on:click={() => (input += '-')}>-</button>
	<button on:click={() => (input += '1')}>1</button>
	<button on:click={() => (input += '3')}>3</button>
	<button on:click={() => (input += '*')}>*</button>
	<button on:click={() => (input += '7')}>7</button>
	<button
		on:click={() => {
			calculate();
		}}>=</button
	>
	<button
		on:click={() => {
			input = '';
			result = 0;
		}}>C</button
	>
</div>

<style>
	* {
		font-family: 'Comic Sans MS';
	}

	button {
		width: 200px;
		height: 200px;
		font-size: 50px;
	}
</style>

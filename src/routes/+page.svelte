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

<body>
	<h1>
		{#if result > 1}
			{result}
		{/if}
		Welcome to my Calculator
	</h1>
	<p class="output">Output: {input || result}</p>
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
</body>

<style>
	@keyframes move_button {
		0% {
			background-color: red;
		}

		25% {
			background-color: yellow;
		}

		50% {
			background-color: #b7ff00;
		}

		75% {
			background-color: #b00b69;
		}

		100% {
			background-color: aqua;
		}
	}

	* {
		font-family: 'Comic Sans MS';
	}

	body {
		background-color: red;
		animation-name: move_button;
		animation-duration: 10s;
		animation-iteration-count: infinite;
	}

	button {
		width: 200px;
		height: 200px;
		font-size: 50px;
		border-radius: 500px;
	}

	button:hover {
		background-color: aqua;
		color: blue;
	}

	.output {
		font-size: 28px;
		color: green;
	}
</style>

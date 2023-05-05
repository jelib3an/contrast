<script lang="ts">
	let opacity = 100;

	const min = 60;
	const max = 100;
	const step = 5;

	function decrease() {
		const newOpacity = opacity - step;
		opacity = newOpacity < min ? min : newOpacity;
	}

	function increase() {
		const newOpacity = opacity + step;
		opacity = newOpacity > max ? max : newOpacity;
	}
</script>

<div class="container">
	<div class="black" style={`--opacity: ${opacity / 100};`}>
		<div class="text">
			<p>Contrast</p>
			<p>對比</p>
		</div>
	</div>
	<div class="controls">
		<input on:click={decrease} class="button" type="button" value="-" />
		<input bind:value={opacity} class="slider" type="range" {min} {max} />
		<input on:click={increase} class="button" type="button" value="+" />
	</div>
</div>

<style>
	.container {
		padding: 1rem;
	}

	.slider {
		flex: 1 1 auto;
		margin: 0 1rem 0 1rem;
	}

	.black {
		position: relative;
		width: 100%;
		height: 25rem;
		background-color: rgba(0, 0, 0, var(--opacity));
	}

	.text {
		position: absolute;
		margin: 0;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
		font-size: 5rem;
		text-transform: uppercase;
	}

	.text p {
		text-align: center;
		line-height: 0;
	}

	.controls {
		margin-top: 0.5rem;
		display: flex;
	}

	.button {
		flex: none;
		width: 4rem;
		height: 4rem;
	}
</style>

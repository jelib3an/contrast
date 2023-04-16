<script lang="ts">
	let opacity = 75;
</script>

<div class="container">
	<input bind:value={opacity} class="slider" type="range" min="60" max="100" />
	<div class="black" style={`--opacity: ${opacity / 100};`}>
		<div class="text">
			<p>Contrast</p>
			<p>對比</p>
		</div>
	</div>
</div>

<style>
	.container {
		padding: 10px;
	}

	.slider {
		width: 100%;
	}

	.black {
		position: relative;
		width: 100%;
		height: 200px;
		margin-top: 10px;
		background-color: rgba(0, 0, 0, var(--opacity));
	}

	.text {
		position: absolute;
		margin: 0;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
		font-size: 60px;
		text-transform: uppercase;
	}

	.text p {
		text-align: center;
		line-height: 0;
	}
</style>

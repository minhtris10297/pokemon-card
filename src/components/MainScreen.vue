<template>
	<div class="mainScreen">
		<h1 class="mainTitle">Please Input Your Name</h1>
		<h3 class="inputName">
			<input type="text" id="playerName" />
		</h3>
		<h1 class="mainTitle">Choose Level</h1>
		<div class="chooseLevel">
			<button @click="onStart(16)">
				<span>4x4</span>
				<span>Easy</span>
			</button>
			<button @click="onStart(36)">
				<span>6x6</span>
				<span>Normal</span>
			</button>
			<button @click="onStart(64)">
				<span>8x8</span>
				<span>Hard</span>
			</button>
		</div>
	</div>
</template>

<script>
export default {
	emits: ["onStart"],
	methods: {
		onStart(totalCard) {
			this.$emit("onStart", { totalCard });
		},
	},
};
</script>

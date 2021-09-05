<template>
	<div class="card">
		<div
			class="cardInner"
			:class="{ isFlipped: cardIsFlipped }"
			@click="onToggleFlipCard()"
		>
			<div class="cardFace faceFront">
				<div class="cardContet">Mat Truoc</div>
			</div>
			<div class="cardFace faceBack">
				<div class="cardContet">mat Sau</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	data() {
		return {
			cardIsFlipped: false,
		};
	},
	methods: {
		onToggleFlipCard() {
			this.cardIsFlipped = !this.cardIsFlipped;
		},
	},
};
</script>

<style lang="css" scoped>
.card {
	display: inline-block;
	width: 90px;
	height: 120px;
	margin-right: 1rem;
	margin-bottom: 1rem;
}

.cardInner {
	width: 100%;
	height: 100%;
	transition: transform 0.5s;
	transform-style: preserve-3d;
	cursor: pointer;
	position: relative;
}

.cardInner.cardFlipped {
	transform: rotateY(-180deg);
}

.cardInner.isFlipped {
	background-color: var(--light);
	transform: rotateY(-180deg);
}

.cardFace {
	position: absolute;
	width: 100%;
	height: 100%;
	backface-visibility: hidden;
	overflow: hidden;
	border-radius: 1rem;
	padding: 1rem;
	box-shadow: 0 3px 18px 3px rgba(0, 0, 0, 0.2);
}

.faceBack {
	background-color: var(--light);
	transform: rotateY(-180deg);
}
</style>

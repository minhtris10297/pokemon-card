<template>
	<div id="mainScreen">
		<h1>Good Luck and Have Fun</h1>
		<div>{{cardsContext}}</div>
		<CardFlip v-for="(card, index) in cardsContext" :key="index"/>
	</div>
</template>

<script>
import CardFlip from "./Card";

export default {
	props: {
		cardsContext: {
			type: Array,
			default: function() {
				return [];
			},
		},
	},
	components: {
		CardFlip,
	},
};
</script>

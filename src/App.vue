<template>
	<div class="root">
		<MainScreen v-if="gameState === 'prepare'" @onStart="changeState($event)" />
		<PlayScreen v-if="gameState === 'play'" :cardsContext="setting.cardsContext"/>
		<FunnyFooter />
	</div>
</template>

<script>
import MainScreen from "./components/MainScreen";
import PlayScreen from "./components/PlayScreen";
import FunnyFooter from "./components/FunnyFooter";
import { shuffleArray } from "./utils/array.js";

export default {
	name: "App",
	data() {
		return {
			// gameState => game state: prepare - play - result
			gameState: "prepare",
			setting: {
				totalCard: 0,
				cardsContext: [],
				startedAt: null,
			},
		};
	},
	components: {
		MainScreen,
		PlayScreen,
		FunnyFooter,
	},
	methods: {
		changeState(configs) {
			this.setting.totalCard = configs.totalCard;
			const halfOfListPairOfCards = Array.from({ length: this.setting.totalCard / 2}, (_, i) => i + 1);
			this.setting.cardsContext = shuffleArray(shuffleArray([...halfOfListPairOfCards, ...halfOfListPairOfCards]));
			this.setting.startedAt = new Date().getTime();

			this.gameState = "play";
		},
	},
};
</script>

<template>
    <MainScreen v-if="gameState === 'prepare'" @onStart="changeState($event)"/>
    <PlayScreen v-if="gameState === 'play'" />
    <FunnyFooter />
</template>

<script>
import MainScreen from "./components/MainScreen"
import PlayScreen from "./components/PlayScreen"
import FunnyFooter from "./components/FunnyFooter"

export default {
  name: "App",
  data() {
    return {
        // gameState => game state: prepare - play - result
        gameState: "prepare",
    }
  },
  components: {
    MainScreen, PlayScreen, FunnyFooter
  },
  methods: {
    changeState(config) {
        console.log("aaa", config);
        this.gameState = "play";
    }
  },
};
</script>

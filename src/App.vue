<template>
    <MainScreen />
    <FunnyFooter />
</template>

<script>
import MainScreen from "./components/MainScreen"
import FunnyFooter from "./components/FunnyFooter"

export default {
  name: "App",
  components: {
    MainScreen, FunnyFooter
  },
};
</script>

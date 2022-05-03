<template>
  <h1>Reaction Timer</h1>
  <button @click="start" :disabled="isPlaying">play</button>
  <ClickBlock v-if="isPlaying" :delay="delay" @end="endGame" />
  <ClickResults v-if="score !== null" :score="score" />
</template>

<script>
import ClickBlock from "./components/ClickBlock.vue";
import ClickResults from "./components/ClickResults.vue";
export default {
  name: "App",
  components: { ClickBlock, ClickResults },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
    };
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      this.score = null;
    },
    endGame(reactionTime) {
      this.score = reactionTime;
      this.isPlaying = false;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

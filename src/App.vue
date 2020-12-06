<template>
  <h1>REACTION TIMER</h1>
  <button v-on:click="start" v-bind:disabled="isPlaying">Start</button>
  <Block v-if="isPlaying" v-bind:delay="delay" v-on:end="endGame" />
  <Results v-if="showResults" v-bind:score="score" />
</template>

<script>
import Block from "./components/Block.vue";
import Results from "./components/Results.vue";
export default {
  name: "App",
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: 0,
      showResults: false,
    };
  },
  components: { Block, Results },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      console.log(this.delay);
      this.showResults = false;
    },
    endGame(reactionTime) {
      this.score = reactionTime;
      this.showResults = true;
      this.isPlaying = false;
    },
  },
};
</script>

<style>
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444444;
  margin-top: 60px;
}
</style>

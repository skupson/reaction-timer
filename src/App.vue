<template>
  <h1>REACTION TIMER</h1>
  <Results v-bind:score="score" />
  <button ref="button" v-on:click="start" v-bind:disabled="isPlaying">
    Start
  </button>
  <Block v-if="isPlaying" v-bind:delay="delay" v-on:end="endGame" />
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
    };
  },
  components: { Block, Results },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      console.log(this.delay);
      this.score = 0;
      this.$refs.button.classList.add("disabled");
    },
    endGame(reactionTime) {
      this.score = reactionTime;
      this.isPlaying = false;
      this.$refs.button.classList.remove("disabled");
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

<template>
  <h1>Reaction Timer</h1>
  <button v-on:click="start" v-bind:disabled="isPlaying">Start</button>
  <Block v-if="isPlaying" v-bind:delay="delay" />
</template>

<script>
import Block from "./components/Block.vue";
export default {
  name: "App",
  data() {
    return {
      isPlaying: false,
      delay: null,
    };
  },
  components: { Block },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      console.log(this.delay);
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
  color: #444444;
  margin-top: 60px;
}
</style>

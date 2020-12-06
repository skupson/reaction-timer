<template>
  <div class="block" v-if="showBlock" v-on:click="stopTimer">click me</div>
</template>

<script>
export default {
  props: ["delay"],
  data() {
    return { showBlock: false, timer: null, reactionTime: 0 };
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true;
      this.stratTimer();
    }, this.delay);
  },
  methods: {
    stratTimer() {
      this.timer = setInterval(() => {
        this.reactionTime += 10;
      }, 10);
    },
    stopTimer() {
      clearInterval(this.timer);
      this.$emit("end", this.reactionTime);
    },
  },
};
</script>

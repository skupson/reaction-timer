<template>
  <div ref="results" class="results">
    <p>Your reaction time is {{ score }} ms</p>
  </div>
</template>

<script>
export default {
  props: ["score"],
};
</script>

<style>
</style>
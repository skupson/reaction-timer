<template>
  <div class="results">
    <p>Reaction time is {{ score }} ms</p>
  </div>
</template>

<script>
export default {
  props: ["score"],
};
</script>

<style>
</style>
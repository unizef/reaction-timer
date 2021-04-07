<template>
  <p class="results">
    Your reaction time is: <span>{{ score }} ms</span>
  </p>
</template>

<script>
export default {
  props: ["score"],
};
</script>

<style>
.results {
  font-size: 1.3rem;
  margin-top: 2rem;
}
.results span {
  font-family: monospace;
  font-weight: 550;
}
</style>

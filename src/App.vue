<template>
  <div>
    <h1>Reaction Timer Game</h1>
    <button class="btn" :click="start">Start</button>
  </div>
</template>

<script>
import "./assets/styles/global.css";

export default {
  name: "App",
  components: {},
};
</script>

<style>
#app {
  text-align: center;
  color: var(--primary-color);
  margin-top: 60px;
}
</style>

<template>
  <div>
    <h1>Reaction Timer Game</h1>
    <button class="btn" @click="start">Start</button>
  </div>
</template>

<script>
import "./assets/styles/global.css";

export default {
  name: "App",
  components: {},
  data() {
    return {
      isPlaying: false,
      delay: null,
    };
  },
  methods: {
    start() {
      this.isPlaying = true;
      this.delay = 2000 + Math.random() * 5000;
      console.log(this.delay);
    },
  },
};
</script>

<style>
#app {
  text-align: center;
  color: var(--primary-color);
  margin-top: 60px;
}
</style>

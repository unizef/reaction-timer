<template>
  <div>
    <h1>Reaction Timer Game</h1>
    <button class="btn" @click="start" :delay="delay" :disabled="isPlaying">
      Start
    </button>
    <Block v-if="isPlaying" />
  </div>
</template>

<script>
import "./assets/styles/global.css";
import Block from "./components/Block";

export default {
  name: "App",
  components: { Block },
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
h1 {
  margin-bottom: 50px;
}
#app {
  text-align: center;
  color: var(--primary-color);
  margin-top: 60px;
}
</style>

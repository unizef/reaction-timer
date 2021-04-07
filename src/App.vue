<template>
  <div>
    <h1>Reaction Timer Game</h1>
    <button class="btn" @click="start" :disabled="isPlaying">
      Start
    </button>
    <Results v-if="showResults" :score="score" />
    <Block v-if="isPlaying" :delay="delay" @end="endGame" />
  </div>
</template>

<script>
import "./assets/styles/global.css";
import Block from "./components/Block";
import Results from "./components/Results";

export default {
  name: "App",
  components: { Block, Results },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false,
    };
  },
  methods: {
    start() {
      this.isPlaying = true;
      this.delay = 2000 + Math.random() * 5000;
      this.showResults = false;
    },
    endGame(reactionTime) {
      this.isPlaying = false;
      this.score = reactionTime;
      this.showResults = true;
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
  margin-top: 8rem;
}
</style>

<template>
  <div v-if="showBlock" class="block animal" @click="stopTimer">
    {{ this.animals[this.animal] }}
  </div>
</template>

<script>
import "../assets/styles/global.css";
export default {
  props: ["delay"],
  data() {
    return {
      animal: null,
      animals: [
        "🐶",
        "🐯",
        "🐼",
        "🦊",
        "🐻",
        "🐸",
        "🐰",
        "🐷",
        "🐮",
        "🐱",
        "🐺",
        "🦁",
      ],
      count: 3,
      showBlock: false,
      timer: null,
      reactionTime: 0,
    };
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true;
      this.startTimer();
      this.randomAnimal();
    }, this.delay);
  },

  methods: {
    randomAnimal() {
      this.animal = Math.floor(Math.random() * 5);
    },
    startTimer() {
      this.timer = setInterval(() => {
        this.reactionTime += 10;
      }, 10);
    },
    stopTimer() {
      clearInterval(this.timer);
      console.log("reaction time: ", this.reactionTime);
    },
  },
};
</script>

<style>
.animal {
  font-size: 10rem;
  padding: 15px;
  cursor: pointer;
}
/* .block {
  width: 400px;
  border-radius: 20px;
  background: var(--secondary-color);
  color: #fff;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
} */
</style>

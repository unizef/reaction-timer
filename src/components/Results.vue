<template>
  <div>
    <p class="results">
      Your reaction time is: <span>{{ score }} ms</span>
    </p>
    <p class="rank">
      {{ rank }} <span>{{ animal }}</span>
    </p>
  </div>
</template>

<script>
export default {
  props: ["score"],
  data() {
    return {
      rank: null,
      animal: "",
    };
  },
  mounted() {
    if (this.score < 360) {
      this.rank = "As fast a deer!";
      this.animal = "🦌";
    } else if (this.score < 390) {
      this.rank = "Not bad for a raccoon!";
      this.animal = "🦝";
    } else {
      this.rank = "Snail pace....";
      this.animal = "🐌";
    }
  },
};
</script>

<style>
.results {
  font-size: 1.3rem;
  margin-top: 2.5rem;
}
.results span {
  font-family: monospace;
  font-weight: 550;
  color: var(--secondary-color);
}

.rank {
  margin-top: 2rem;
  color: teal;
  font-weight: 600;
  font-size: 1.2rem;
}

.rank span {
  font-size: 1.6rem;
}
</style>

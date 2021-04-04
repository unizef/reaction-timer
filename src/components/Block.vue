<template>
  <div v-if="showBlock" class="block">
    Click Me
  </div>
</template>

<script>
import "../assets/styles/global.css";
export default {
  props: ["delay"],
  data() {
    return {
      showBlock: false,
    };
  },

  mounted() {
    setTimeout(() => {
      this.showBlock = true;
    }, this.delay);
  },
};
</script>

<style>
.block {
  width: 400px;
  border-radius: 20px;
  background: var(--secondary-color);
  color: #fff;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
}
</style>

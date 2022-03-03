<template>
  <div>
    <h1>Reaction time: {{ score }} ms</h1>
    <p>Rank {{ rank }}</p>
  </div>
</template>

<script>
export default {
  props: ["score", "delay"],
  data() {
    return {
      rank: null,
    };
  },
  mounted() {
    if (this.score < 1000) {
      this.rank = "Newbie";
    } else if (this.score < 2000) {
      this.rank = "Amateur";
    } else if (this.score < 3000) {
      this.rank = "Pro";
    } else {
      this.rank = "Master";
    }
  },
};
</script>

<style>
</style>
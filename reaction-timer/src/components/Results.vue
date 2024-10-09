<template>
  <div>
    <p>Reaction time: {{ score }} ms</p>
    <p class="rank">{{ rank }}</p>
  </div>
</template>

<script>
export default {
  props: ["score"],
  data() {
    return {
      rank: null,
    };
  },
  mounted() {
    if (this.score < 250) {
      this.rank = "F1 driver reaction time";
    } else if (this.score < 400) {
      this.rank = "Average reaction time";
    } else {
      this.rank = "Wake up!";
    }
  },
};
</script>

<style>
.rank {
  font-size: 1.5rem;
  color: #0faf87;
  font-weight: bold;
}
</style>
<template>
  <div class="results" :class="{ fast: this.score <= 300, slow: this.score > 300 }">
    Your reaction time is {{ score }} ms
  </div>
</template>

<script>
export default {
  props: ["score"],
};
</script>

<style scoped>
.results.fast {
  width: 400px;
  border-radius: 10px;
  background: lightgreen;
  color: darkgreen;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
}

.results.slow {
  width: 400px;
  border-radius: 10px;
  background: crimson;
  color: white;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
}
</style>

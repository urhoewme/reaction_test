<template>
  <Navigation />
  <h1>Reaction test</h1>
  <button :disabled="isPlaying" @click="start">Start new game</button>
  <Block :delay="delay" v-if="isPlaying" @end="endGame" />
  <Results :score="score" v-if="showResults" />
  <Alert v-if="preFire" />
  <div v-if="isPlaying && !isShown" @click="preFired" class="alert-area"></div>
</template>

<script>
import Block from "@/components/Block.vue";
import Results from "@/components/Results.vue";
import Alert from "@/components/Alert.vue";
import Navigation from "@/components/Navigation.vue";

export default {
  name: "App",
  components: {
    Block,
    Results,
    Alert,
    Navigation,
  },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false,
      preFire: false,
      isShown: false,
    };
  },
  methods: {
    start() {
      this.isPlaying = true;
      this.delay = 2000 + Math.random() * 5000;
      this.showResults = false;
      this.preFire = false;
      this.isShown = false;
      setTimeout(() => {
        this.isShown = true;
      }, this.delay);
    },
    endGame(reactionTime) {
      this.score = reactionTime;
      this.isPlaying = false;
      this.showResults = true;
    },
    preFired() {
      console.log(this.isPlaying, this.isShown);
      if (this.isPlaying === true && this.isShown === false) {
        this.preFire = true;
        this.isPlaying = false;
      }
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  font-family: "Montserrat", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: teal;
}

h1 {
  margin-top: 30px;
}

button {
  font-family: "Montserrat", sans-serif;
  font-size: 16px;
  padding: 12px 18px;
  border-radius: 8px;
  border: 1px solid teal;
  margin-top: 25px;
}

.alert-area {
  top: 0;
  position: fixed;
  width: 100%;
  height: 100%;
  margin-top: 145px;
}
</style>

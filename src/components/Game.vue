<template>
  <div id="game">
    <h2>NCT Reaction Game with Vue</h2>
    <button id="startbtn" @click="start" :disabled="isPlaying">Start</button>
    <p v-if="isWaiting">Wait...</p>
    <Results :score="score" v-if="showResults" />
    <Block
      v-if="isPlaying"
      :delay="delay"
      @end="endGame"
      @blockSpawned="hideWaitingText"
    />
  </div>
</template>

<script>
import Block from "./Block.vue";
import Results from "./Results.vue";
export default {
  components: {
    Block,
    Results,
  },
  data() {
    return {
      delay: null,
      isPlaying: false,
      score: null,
      showResults: false,
      isWaiting: false,
    };
  },
  methods: {
    start() {
      this.showResults = false;
      this.isPlaying = true;
      this.isWaiting = true;
      this.delay = 2000 + Math.random() * 5000;
    },
    endGame(reactionTime) {
      this.score = reactionTime;
      this.isPlaying = false;
      this.showResults = true;
    },
    hideWaitingText() {
      this.isWaiting = false;
    },
  },
};
</script>

<style>
#game {
  text-align: -webkit-center;
}
#startbtn {
  cursor: pointer;
}
#startbtn:disabled {
  cursor: not-allowed;
}
</style>
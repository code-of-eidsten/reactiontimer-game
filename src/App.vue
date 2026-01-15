<template>
  <h1>Reaction Timer Game</h1>
  <h2>{{ score !== null ? `Your Reaction Time: ${score} ms!` : '' }}</h2>
  <button @click="start" :disabled="isPlaying">Start Game</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame" />
</template>

<script>
import Block from './components/Block.vue';

export default {
  name: 'App',
  components: {
    Block
  },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
    }
  },
  methods: {
    start() {
      this.delay = Math.floor(Math.random() * 5000) + 2000;
      this.isPlaying = true;
    },
    endGame(reactionTime) {
      this.score = reactionTime;
      this.isPlaying = false;
    }
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: rgb(100, 117, 230);
  margin-top: 60px;
}
</style>

<template>
  <h1>Reaction Game 🏁</h1>
  <button @click="start" :disabled="isPlaying">Play</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame" />
  <Result v-if="showResult" :showScore="score" />
</template>

<script>
import Block from "./components/Block.vue";
import Result from "./components/Result.vue";

export default {
  name: "App",
  components: {
    Block, Result
  },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResult: false
    };
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      this.showResult = false
    },
    endGame(reactionTime){
      this.score = reactionTime;
      this.isPlaying = false;
      this.showResult = true
    }
  }
};
</script>

<style>
#app {
  font-family: "Poppins", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1 {
  color: #eeeeee;
}

button{
  padding: 10px 30px 10px 30px;
  border: 2px solid #DDDDDD;
  border-radius: 4px;
  background: none;
  color: #DDDDDD;
  transition: transform 0.3s ease;
}

button:hover{
  background: #76885B;
  cursor: pointer;
  transform: scale(1.1);
}

</style>

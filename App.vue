<template>
  <h1>HOW FAST CAN U CATCH MEE !!</h1>

  <button @click="start" :disabled="isPlaying"> CLICK TO PLAY </button>

  <div v-if="isPlaying">
    <Block :delay="delay" @endGame="endGame"/>
  </div>

  <!-- <p>RESULT IS {{ score }} ms</p> -->
  <div v-if="end">
    <Result :score="score"/>
  </div>
  

  <myBlock/>

</template>

<script>

import Block from './components/Block.vue';
import myBlock from './components/myBlock.vue';
import Result from './components/Result.vue';

export default {
  name: 'App',
  components: {
    Block,
    myBlock,
    Result
  },
  data(){
    return {
      isPlaying: false,
      delay:null,
      score:0,
      end:false
    }
  },
  methods: {
    start(){
      this.isPlaying=true;
      this.delay=2000+Math.random()*7000;
    },
    endGame(score){
      this.score=score;
      this.isPlaying=false;
      this.end=true;
    }

  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
button{
  margin-bottom: 20px;
  padding-top: 15px;
  padding-bottom: 10px;
  box-shadow: 5px 5px 5px;
  border-radius: 10px;
  border: .3px solid grey;
  font-weight: 600;
  background-color: crimson;
  color: rgb(220, 216, 210);
}
button:hover{
  background-color: #2c3e50;
  color: blanchedalmond;
}
:disabled{
  color: #2c3e50;
  background-color: rgb(226, 171, 171);
}
</style>

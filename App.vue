<template>
  <h1>HOW FAST CAN U CATCH MEE !!</h1>

  <button @click="start" :disabled="isPlaying"> CLICK TO PLAY </button>

  <div v-if="isPlaying">
    <Block :delay="delay" />
  </div>

  <myBlock/>

</template>

<script>

import Block from './components/Block.vue';
import myBlock from './components/myBlock.vue';

export default {
  name: 'App',
  components: {
    Block,
    myBlock
  },
  data(){
    return {
      isPlaying: false,
      delay:null
    }
  },
  methods: {
    start(){
      this.isPlaying=true;
      this.delay=2000+Math.random()*7000;
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
</style>

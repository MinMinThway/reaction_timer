<template>
  <h3>How Fast Can You Catche Me!</h3>
  <button @click="start" :disabled="isPlaying">Play</button>
  <div v-if="isPlaying">
    <Block :delay = "delay" @endGame="endGame"/>
  </div>
  <div v-if="end">
    <Result :score = "score"/>
  </div>
  
</template>
<script>
import Block from './components/Block.vue';
import Result from './components/Result.vue';
export default {
  data(){
    return {
      isPlaying : false,
      delay : null,
      score : 0,
      end : false,
    }
  },
  components:{
    Block,
    Result,
  },
  methods:{
    start(){
      this.isPlaying=true;
      this.delay = 2000+Math.random()*5000;
     
    },
    endGame(score){
      this.score += score;
      this.isPlaying=false;
      this.end=true;
    }
  }
}
</script>
<style >
#app{
  text-align: center;
  margin: 50px auto;

}
</style>>


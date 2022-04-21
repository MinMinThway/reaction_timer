<template>
  <div class="block" v-if="showDelay" @click="stopTimer">
      Click Me {{ delay }}
  </div>
</template>

<script>
export default {
    props:['delay'],
    data(){
        return {
            showDelay : false,
            score : 0,
            time : null,
        }
    },
    methods:{
        startTimer(){
            this.time =+ setInterval(() => {
                this.score += 50;
            }, 50);
        },
        stopTimer(){
            clearInterval(this.time);
            this.$emit("endGame", this.score)
        }
    },
    mounted(){
      setTimeout(() => {
          this.showDelay=true;
          this.startTimer();
      }, this.delay)
    },
    
}
</script>

<style>
    .block{
        width: 300px;
        height: 200px;
        background-color: aqua;
       margin: 30px auto;
    }
</style>
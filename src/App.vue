<template>
  <div>
      <div class="text-center mt-16">
          <h1 class="text-2xl ">How fast Can U Catch Me?</h1>
          <button @click="start" class=" bg-red-500 px-4 mt-7 p-1 text-2xl text-white rounded-lg" :disabled="isPlaying">Play</button>
      </div>
     <div class="text-center text-xl mt-5" v-if="end">
       <Result :score="score"/>
     </div>
      <div v-if="isPlaying">
        <Block :delay="delay" @endGame="endGame"/>
      </div>
      
  </div>
</template>

<script>
import Block from './components/Block.vue'
import Result from './components/Result.vue'
  export default {
    components: {
      Block,Result
    },
    data() {
      return {
        isPlaying: false,
        delay: null,
        score:0,
        end:false
      }
    },
    methods: {
      start() {
        this.isPlaying = true;
        this.delay = 2000+Math.random()*3000
      },
       endGame(score){
      this.score = score,
      this.isPlaying = false,
      this.end =true
    }
    },
   
  }
</script>

<style scoped>

</style>
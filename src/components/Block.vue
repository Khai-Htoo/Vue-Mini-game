<template>
   <div v-if="block">
     <div class="mt-10  flex justify-center ">
         <h1 class="bg-cyan-400 p-32" @click="stopTimer">Click here</h1>
    </div>
   </div>
</template>

<script>
    export default {
        props:['delay'],
        data() {
            return {
                block: false,
                score : 0,
                timer:null
            }
        },
        mounted () {
            setTimeout(() => {
              this.block = true  ;
              this.startTimer()
            }, this.delay);
        },
      methods: {
        startTimer() {
            this.timer=setInterval(() => {
                this.score+=50
            }, 50);
        },
        stopTimer(){
            clearInterval(this.timer);
            this.$emit("endGame",this.score)
        }
      },
    }
</script>

<style scoped>

</style>
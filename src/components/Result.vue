<template>
    <div>
        result is {{score}} ms
        <div class="mt-3" v-if="score < 300">
            <span class="bg-green-200 p-2 ">HaHa WellPlayed Bro! You are too fast</span>
        </div>
           <div class="mt-3" v-else-if="score > 300 && score < 1000">
            <span class="bg-yellow-200 p-2 ">Hey Hey Not bad!But you are little slow</span>
        </div>
        <div class="mt-3" v-else-if="score > 1000 ">
            <span class="bg-red-200 p-2 ">humm!You are slow hand bro!</span>
        </div>
    </div>
</template>

<script>
    export default {
        props:['score']
    }
</script>


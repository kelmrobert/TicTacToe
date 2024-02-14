<script setup>

import Grid from "@/components/Grid.vue";
import Welcome from "@/components/Welcome.vue";

const winCombinations = {
  0: [1,2,3],
  1: [4,5,6],
  2: [7,8,9],
  3: [1,4,7],
  4: [2,5,8],
  5: [3,6,9],
  6: [1,5,9],
  7: [3,5,7],
}

let gameStarted = false;

</script>

<template>
    <div class="" v-if="!gameStarted">
        <Welcome />
    </div>
    <div class="container" v-if="gameStarted">
        <Grid />
    </div>
</template>

<style scoped>


</style>

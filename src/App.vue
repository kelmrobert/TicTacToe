<script setup>
import Grid from "@/components/Grid.vue";

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

let xValues = [1,2,3]
let oValues = [4,5,6]
let player1 = true

const handleCellClick = (id) => {
  console.log("Klick auf Zelle " + id)
  update(id)
}

function update(id) {
  console.log(xValues)
  if (player1) {
    xValues.push(id)
  } else {
    oValues.push(id)
  }
  player1 = !player1
  console.log(xValues)
}

</script>

<template>
  <h4 v-if="player1">Spieler 1 ist am Zug</h4>
  <h4 v-if="!player1">Spieler 2 ist am Zug</h4>
  <Grid :xValues="xValues" :oValues="oValues" @cellClicked="handleCellClick"></Grid>
</template>

<style scoped>


</style>

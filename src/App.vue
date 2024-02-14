<script setup>
import 'bootstrap';
import { ref } from 'vue';
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

let gameStarted = ref(true);
let xValues = ref([]);
let oValues = ref([]);
let player1 = ref(true);
let player1Win = ref();

function startGame(){
    gameStarted.value = true;
}

function handleCellClick(id) {

    if(xValues.value.includes(id) || oValues.value.includes(id)) {
        return
    }

    if(player1) {
        xValues.value.push(id)
    } else {
        oValues.value.push(id)
    }

    checkWinner()

    player1 = !player1
}

function checkWinner(){

    for (let i = 0; i < Object.keys(winCombinations).length; i++) {
        let winCombination = winCombinations[i]
        let xCount = 0
        let oCount = 0

        for (let j = 0; j < winCombination.length; j++) {
            if(xValues.value.includes(winCombination[j])) {
                xCount++
            } else if(oValues.value.includes(winCombination[j])) {
                oCount++
            }
        }

        if(xCount === 3) {
            player1Win.value = true
        } else if(oCount === 3) {
            player1Win.value = false
        }

        // TODO DO SOMETHING
    }
}

</script>

<template>
    <div class="container">
        <div class="justify-content-center align-items-center">
            <div v-if="!gameStarted">
                <Welcome @start-game="startGame"/>
            </div>
            <div v-if="gameStarted">
                <Grid :xValues="xValues" :oValues="oValues" @cellClicked="handleCellClick" />
            </div>
        </div>
    </div>
</template>

<style scoped>


</style>

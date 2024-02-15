<script setup>
import 'bootstrap';
import {onMounted, ref} from 'vue';
import Grid from "@/components/Grid.vue";
import Welcome from "@/components/Welcome.vue";
import Title from "@/components/Title.vue";
import GameOver from "@/components/GameOver.vue";

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

let gameStarted = ref(false);
let xValues = ref([]);
let oValues = ref([]);
let player1 = ref(true);
let player1Win = ref();
let gameOver = ref(false);
let player1start = ref(true);

function startGame(){
    gameStarted.value = true;
}

function handleCellClick(id) {

    if(xValues.value.includes(id) || oValues.value.includes(id)) {
        if(player1.value && oValues.value.includes(id)) {
            oValues.value = oValues.value.filter(value => value !== id)
         } else {
            return
         }
    }

    if(player1.value) {
        xValues.value.push(id)
    } else {
        if(possibleWin(id)){
            return;
        }
        oValues.value.push(id)
    }

    checkWinner()
    checkDraw()

    player1.value = !player1.value
}

function possibleWin(id){
    let oValuesCopy = oValues.value.slice()
    oValuesCopy.push(id)

    for (let i = 0; i < Object.keys(winCombinations).length; i++) {
        let winCombination = winCombinations[i]
        let oCount = 0

        for (let j = 0; j < winCombination.length; j++) {
            if(oValuesCopy.includes(winCombination[j])) {
                oCount++
            }
        }

        if(oCount === 3) {
            return true
        }
    }
    return false
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
            gameOver.value = true
        } else if(oCount === 3) {
            player1Win.value = false
            gameOver.value = true
        }
    }
}

function checkDraw(){
    if(xValues.value.length + oValues.value.length === 9) {
        player1Win.value = null
        gameOver.value = true
    }
}

function restartGame() {
    xValues.value = []
    oValues.value = []
    player1.value = !player1start.value
    player1Win.value = null
    gameOver.value = false
}

</script>

<template>
    <div class="container">
        <div class="d-flex justify-content-center align-items-center vh-100">
            <div class="text-center">
                <GameOver v-if="gameOver" @restart="restartGame"/>
                <div v-if="!gameStarted">
                    <Welcome @start-game="startGame"/>
                </div>
                <div v-if="gameStarted">
                    <Title :player1="player1"/>
                    <Grid :xValues="xValues" :oValues="oValues" @cellClicked="handleCellClick" />
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>


</style>

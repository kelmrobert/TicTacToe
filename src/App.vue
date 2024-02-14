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

    player1 = !player1
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

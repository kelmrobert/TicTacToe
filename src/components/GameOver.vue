<script setup>

import {onMounted} from "vue";

const emit = defineEmits(['restart-game']);

function restartGame() {
    emit('restart');
}

</script>

<template>
    <div class="backdrop">
        <div class="game-over-box">
            <h1 class="mb-4">Player 1 won!</h1>
            <p class="mb-4">This result is based solely on the course of<br> the game and the unique abilities of player 1.</p>
            <button @click="restartGame" class="btn btn-primary">Start Again</button>
        </div>
    </div>
</template>

<style scoped>
.backdrop {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    display: flex;
    justify-content: center;
    align-items: center;
}

.game-over-box {
    background-color: white;
    padding: 100px;
    border-radius: 10px;
    text-align: center;
    vertical-align: center;
}
</style>
<script setup>

    const emit = defineEmits(['startGame']);

    function changeLocation(event){
        let button = event.target;
        button.style.position = 'absolute';
        button.style.left = Math.random() * window.innerWidth + 'px'
        button.style.top = Math.random() * window.innerHeight + 'px'
    }

    function handleStartGame(){
        emit('startGame');
    }

</script>

<template>
    <div>
        <h1 class="text-primary-emphasis">Can you beat your friend? Find out!</h1>
    </div>
    <div class="mt-5">
        <button class="btn btn-outline-success me-3" @click="handleStartGame">Start Game</button>
        <button class="btn btn-outline-danger" @mouseover="changeLocation">Instructions</button>
    </div>
</template>

<style scoped>

</style>
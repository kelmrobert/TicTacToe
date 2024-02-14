<script setup>

    function changeLocation(event){
        let button = event.target;
        button.style.position = 'absolute';
        button.style.left = Math.random() * window.innerWidth + 'px'
        button.style.top = Math.random() * window.innerHeight + 'px'
    }
</script>

<template>
    <div>
        <h1 class="text-primary-emphasis">Ready to Loose?</h1>
    </div>
    <div class="mt-5">
        <button class="btn btn-outline-success me-3">Spiel starten</button>
        <button class="btn btn-outline-danger" @mouseover="changeLocation">Hilfe</button>
    </div>
</template>

<style scoped>

</style>
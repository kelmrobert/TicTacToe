<script setup>

    function changeLocation(event){
        let button = event.target;
        button.style.position = 'absolute';
        button.style.left = Math.random() * window.innerWidth + 'px'
        button.style.top = Math.random() * window.innerHeight + 'px'
    }
</script>

<template>
    <h1 class="text-primary-emphasis">Ready to Loose?</h1>
    <button class="btn btn-outline-success">Ich versuche mein Glück</button>
    <button class="btn btn-outline-danger" @mouseover="changeLocation">Hilfe</button>
</template>

<style scoped>

</style>
<script setup>

    const props = defineProps({
        player1: Boolean
    });

</script>

<template>
    <h2 v-if="props.player1" class="mb-5">Robert ist am Zug!</h2>
    <h2 v-if="!props.player1" class="mb-5">Spieler 2 ist am Zug!!</h2>
</template>

<style scoped>

</style>
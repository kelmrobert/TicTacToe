<script setup>

    const props = defineProps({
        player1: Boolean
    });

</script>

<template>
    <h2 v-if="props.player1" class="mb-5">Player 1's turn!</h2>
    <h2 v-if="!props.player1" class="mb-5">Player 2's turn!</h2>
</template>

<style scoped>

</style>
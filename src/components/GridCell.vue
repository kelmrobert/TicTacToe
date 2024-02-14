<script setup>

import Cross from "@/components/Cross.vue";
</script>

<template>
    <div class="square">
        <Cross />
    </div>
</template>

<style scoped>
    .square {
        width: 100px;
        height: 100px;
        border: 2px solid gray;
        display: flex;
        justify-content: center;
        align-items: center;
    }
</style>
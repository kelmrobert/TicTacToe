<script setup>

import GridCell from "@/components/GridCell.vue";
</script>

<template>
    <div class="grid" >
        <GridCell v-for="n in 9" :id="n"/>
    </div>
</template>

<style scoped>
    .grid {
        display: grid;
        gap: 1px;
        grid-template-columns: repeat(3, 1fr);
    }
</style>
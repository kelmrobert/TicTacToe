<script setup>
import GridCell from "@/components/GridCell.vue";

// Define props
const props = defineProps({
    xValues: Array,
    oValues: Array,
});
</script>

<template>
    <div class="grid" >
        <GridCell v-for="n in 9" :id="n" :icon="xValues.includes(n) ? 'x' : oValues.includes(n) ? 'o' : undefined"/>
    </div>
</template>

<style scoped>
    .grid {
        display: grid;
        gap: 1px;
        grid-template-columns: repeat(3, 1fr);
    }
</style>
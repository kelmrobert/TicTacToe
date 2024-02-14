<script setup>
import GridCell from "@/components/GridCell.vue";

const emit = defineEmits(['cellClicked']);

// Define props
const props = defineProps({
    xValues: Array,
    oValues: Array,
});

// Define methods
function handleClick(id){
    emit('cellClicked', id);
    console.log('Cell clicked', id);
}

</script>

<template>
    <div class="grid" >
        <GridCell v-for="n in 9"
                  :id="n"
                  :icon="xValues.includes(n) ? 'x' : oValues.includes(n) ? 'o' : undefined"
                  @cellClicked="handleClick"
        />
    </div>
</template>

<style scoped>
    .grid {
        display: grid;
        gap: 1px;
        grid-template-columns: repeat(3, 1fr);
    }
</style>
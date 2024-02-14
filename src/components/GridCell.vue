<script setup>
import Cross from "@/components/Cross.vue";
import Circle from "@/components/Circle.vue";

const emit = defineEmits(['cellClicked']);

const props = defineProps({
    id: Number,
    icon: String,
});

function handleClick(){
    emit('cellClicked', props.id);
}
</script>

<template>
    <div class="square" @click="handleClick">
        <Cross v-if="icon ===  'x'"/>
        <Circle v-if="icon === 'o'"/>
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
<script setup>
import { ref } from 'vue';
  import Cross from "@/components/Cross.vue";
  import Circle from "@/components/Circle.vue";

const props = defineProps({
    id: {
      type: Number,
      required: true
    },
    xValues: {
      type: Array
    },
    oValues: {
      type: Array
    }
  })

const emit = defineEmits(['cellClicked'])

const handleClick = () => {
  emit('cellClicked', props.id)
}
</script>

<template>
  <div class="grid-item" @click="handleClick">
    <Cross v-if="xValues.includes(id)"/>
    <Circle v-if="oValues.includes(id)"/>
  </div>
</template>

<style scoped>
  .grid-item {
    padding: 20px;
    text-align: center;
    vertical-align: middle;
    border: 1px solid black;
    min-height: 100px;
    min-width: 100px;
  }
</style>
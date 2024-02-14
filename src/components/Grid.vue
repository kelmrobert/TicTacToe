<script setup>
import GridCell from "@/components/GridCell.vue";

defineProps({
  xValues: {
    type: Array,
    required: true
  },
  oValues: {
    type: Array,
    required: true
  }
})

const emit = defineEmits(['cellClicked'])

const handleCellClick = (id) => {
  console.log(id)
  emit('cellClicked', id)
}
</script>

<template>
  <div class="container">
    <div class="row justify-content-center">
      <div class="col-4">
        <div class="grid-container">
          <GridCell :id="1" :xValues="xValues" :oValues="oValues" @cellClicked="handleCellClick"/>
          <GridCell :id="2" :xValues="xValues" :oValues="oValues" @cellClicked="handleCellClick"/>
          <GridCell :id="3" :xValues="xValues" :oValues="oValues" @cellClicked="handleCellClick"/>
          <GridCell :id="4" :xValues="xValues" :oValues="oValues" @cellClicked="handleCellClick"/>
          <GridCell :id="5" :xValues="xValues" :oValues="oValues" @cellClicked="handleCellClick"/>
          <GridCell :id="6" :xValues="xValues" :oValues="oValues" @cellClicked="handleCellClick"/>
          <GridCell :id="7" :xValues="xValues" :oValues="oValues" @cellClicked="handleCellClick"/>
          <GridCell :id="8" :xValues="xValues" :oValues="oValues" @cellClicked="handleCellClick"/>
          <GridCell :id="9" :xValues="xValues" :oValues="oValues" @cellClicked="handleCellClick"/>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>

.grid-container {
  display: inline-grid;
  grid-template-columns: auto auto auto;
  padding: 40px;
}
</style>
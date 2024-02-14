<script setup>

import GridCell from "@/components/GridCell.vue";
</script>

<template>
  <div class="container">
    <div class="row justify-content-center">
      <div class="col-4">
        <div class="grid-container">
          <GridCell/>
          <GridCell/>
          <GridCell/>
          <GridCell/>
          <GridCell/>
          <GridCell/>
          <GridCell/>
          <GridCell/>
          <GridCell/>
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
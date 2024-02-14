<script setup>

import GridCell from "@/components/GridCell.vue";
</script>

<template>
  <div class="container">
    <div class="row justify-content-center">
      <div class="col-4">
        <div class="grid-container">
          <GridCell :id="1"/>
          <GridCell :id="2"/>
          <GridCell :id="3"/>
          <GridCell :id="4"/>
          <GridCell :id="5"/>
          <GridCell :id="6"/>
          <GridCell :id="7"/>
          <GridCell :id="8"/>
          <GridCell :id="9"/>
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
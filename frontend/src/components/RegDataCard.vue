<script setup>
const props = defineProps(['data']);
</script>

<template>
    <div class="border m-2 p-2 bg-light container">
    <div class="d-flex">
      <div class="d-inline px-2 ">Register: <br> Value: </div>
      <div class="d-flex flex-row flex-wrap">
      
        <div class="border px-2 text-center bold" v-for="(column, columnIndex) in data.RegData" :key="columnIndex">
          <b>{{ columnIndex + data.startReg }}</b>
          <br>
          {{ column }}
        </div>
      </div>
    </div>
    </div>
</template>
<script setup>
import ContextMenu from "./ContextMenu.vue";
import {reactive, ref, onMounted} from 'vue'
var showContext = reactive({menu: false})
const props = defineProps(['data']);
const menu = ref(null)

function openContextMenu(e) {
        menu.value.open(e);
    }

onMounted(() => {
})

</script>

<template>
  <div class="border m-2 p-2 bg-light container">
  <div class="d-flex">
    <div class="d-inline px-2 ">Register: <br> Value: </div>
    <div class="d-flex flex-row flex-wrap">
    
      <div class="border px-2 text-center bold" v-for="(column, columnIndex) in data.RegData" :key="columnIndex" @contextmenu.prevent.stop="openContextMenu">
        <b>{{ columnIndex + data.startReg }}</b>
        <br>
        {{ column }}
      </div>  
    </div>
  </div>

  <div>
  <context-menu :display="showContext.menu" ref="menu">
      <ul>
          <li> List item 1 </li>
          <li> List item 2 </li>
      </ul>
  </context-menu>

  </div>
  </div>
</template>
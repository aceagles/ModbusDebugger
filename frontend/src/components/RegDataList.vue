<script setup>
import {EventsOn} from "../../wailsjs/runtime/runtime"
import {reactive, onMounted} from "vue"
import RegDataCard from "./RegDataCard.vue"

const data = reactive({vals: []})

onMounted(() => {
    EventsOn("RegData", (result) => data.vals = result)
})

</script>

<template>
    <div>
        <div v-for="(val, index) in data.vals" :key="index">
            <reg-data-card :data="val" />
        </div>
    </div>
</template>
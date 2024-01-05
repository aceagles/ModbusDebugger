<script setup>
import {CheckSubmit, StopReading} from "../../../wailsjs/go/main/App"
import {reactive} from 'vue'
const formData = reactive("")
</script>

<template>
    <form action="#" @submit.prevent="() => CheckSubmit(formData)">
        <label for="hostname">Hostname: </label>
        <input type="text" id="hostname" v-model="formData" class="form-control">
        <div class="justify-content-center text-center">
            <input type="submit" value="Start"  class="btn btn-dark border m-1">
            <input type="button" value="Stop" @click="StopReading" class="btn btn-dark border ">
        </div>
        <hr>
    </form>
</template>

<style scoped>

</style>


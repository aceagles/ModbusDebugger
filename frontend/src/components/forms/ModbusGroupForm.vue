<script setup>
import {onMounted, ref} from 'vue'
import {UpdateGroups, GetGroups} from "../../../wailsjs/go/main/App"
import {EventsOn} from "../../../wailsjs/runtime/runtime"
const data = ref([{startReg: 0, numReg: 0}])

function addGroup () {
    console.log("Adding Group")
    data.value.push({startReg: 0, numReg: 0})
}

function removeElement(index){
    data.value.splice(index, 1)
}


onMounted(() => {
    GetGroups().then(result => {
        if (result != null) {
            data.value = result 
        }
    })
})

</script>

<template>
    <div>
        <div class="d-flex ">
            <div class="d-inline col-6">Start Reg: </div>
            <div class="d-inline col-6">N: </div>
        </div>
        <div v-for="(group, index) in data" :key="group" class="mt-1">
            <div class="d-flex">
                    <input type="number" name="start_reg" id="StartReg" v-model="group.startReg" class="form-control">
                    <input type="number" name="start_reg" id="NumReg" v-model="group.numReg" class="form-control">
                    <div class="border p-1 justify-content-center text-center mx-1 hover" role="button" @click="() => removeElement(index)">x</div>
            </div>

       </div>
        <div class="p-2 text-center">
            <input type="button" value="Add Group" @click="addGroup" class="btn btn-dark mx-1">
            <input type="button" value="Update" @click="() => UpdateGroups(JSON.stringify(data))" class="btn btn-dark mx-1">
            
        </div>
    </div>
</template>

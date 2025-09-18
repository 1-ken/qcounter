<template>
  <q-page class="flex flex-center text-white">
    <div class="row">
      <q-input
      v-model="data.name"
      placeholder="Counter"
      filled
      color="teal"
      input-class="text-center text-white text-h5"
      />
    </div>
    <div class="row full-width">
      <div class="col text-center">
        <q-btn
        @click="decreaseCounter"
        icon="remove"
        size="xl"
        round
        />
      </div>
      <div class="col text-center text-h2">
        {{data.couter}}
      </div>
      <div class="col text-center">
        <q-btn
        @click="increaseCounter"
        icon="add"
        size="xl"
        round
        />
      </div>
    </div>
    <div class="row">
       <q-btn
       @click="resetCounter"
        icon="restart_alt"
        size="xl"
        round
        />
    </div>
  </q-page>
</template>
<style scoped>
.q-page {
  max-width: 700px;
  margin: 0 auto;
}
</style>

<script setup>
// imports
import { reactive } from 'vue';
// data
const data = reactive({
  couter:0,
  name:''
})
// counter methods
const increaseCounter = () =>{
  data.couter ++
}
const decreaseCounter = () =>{
  if(data.couter > 0){
    data.couter --
  }
}
 const resetCounter = () =>{
    data.couter = 0
  }
</script>

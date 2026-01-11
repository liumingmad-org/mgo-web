<script setup>
import { ref, reactive } from 'vue'
import { addTowNum, haha } from '../utils/test'

defineProps({
  msg: String,
})

const count = ref(0)


let name = haha

let nani = reactive({
  x: 10,
  y: 20,
})

function add() {
  count.value++;

  console.log(addTowNum(100, count.value))

  nani.x++
  nani.y++
}

let show = ref(true)
</script>

<template>
  <h1>{{ msg }}</h1>
  <h1>{{ name }}</h1>

  <input v-model="nani.x" />
  <p>你输入的是{{ nani.x }}, {{ nani.y }}</p>

  <div class="card">
    <button class="count-btn" type="button" @click="add()">count is {{ count }}</button>
  </div>

  <button class="count-btn" type="button" @click="show=!show">show</button>
  <p v-if="show" class="show-view">look me</p>

</template>

<style scoped>
  .count-btn {
    color: brown;
    background-color: white;
  }

  .show-view {
    color: greenyellow;
  }
</style>

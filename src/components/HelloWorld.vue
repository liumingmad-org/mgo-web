<script setup>
import { ref } from 'vue'

defineProps({
  msg: String,
})

const count = ref(0)

function add() {
  count.value++;
}

let name = "Alice"
</script>

<template>
  <h1>{{ msg }}</h1>
  <h1>{{ name }}</h1>

  <div class="card">
    <button class="count-btn" type="button" @click="add()">count is {{ count }}</button>
  </div>

</template>

<style scoped>
  .count-btn {
    color: brown;
    background-color: white;
  }
</style>

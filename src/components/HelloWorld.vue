<script setup>
import { ref } from 'vue'

defineProps({
  msg: String,
})

const count = ref(0)
</script>

<template>
  <h1>{{ msg }}</h1>

  <div class="card">
    <button class="count-btn" type="button" @click="count++">count is {{ count }}</button>
  </div>

</template>

<style scoped>
  .count-btn {
    color: brown;
    background-color: white;
  }
</style>

<script setup>
import { ref, reactive, computed } from 'vue'
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

const author = reactive({
  name: "tom",
  books: [
    "halibote",
    "How to fuck",
    "apue",
    "csapp"
  ]
})

const list = ref([{name: "ming"}, {name: "tom"}, {name: "cat"}])

function add() {
  count.value++;

  console.log(addTowNum(100, count.value))

  nani.x++
  nani.y++

  author.books.push("how to kiss")
}

let show = ref(true)

let bookCount = computed(() => {
  return author.books.length
})

let isActive = ref(true)

const awesome = ref(true)
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

  <p>book count is {{ bookCount }}</p>

  <button class="count-btn" type="button" @click="isActive=!isActive">show class</button>
  <div :class="{ active: isActive }">class active</div>


  <button class="count-btn" @click="awesome = !awesome">Toggle</button>
  <h1 v-if="awesome">Vue is awesome!</h1>
  <h1 v-else>Oh no 😢</h1>

  <template v-if="awesome">
    <h1>Title</h1>
    <p>Paragraph 1</p>
    <p>Paragraph 2</p>
  </template>

  <h1 v-show="awesome">Hello!</h1>

  <li v-for="(item, x) in list">
    {{ item.name }} -- {{ x }}
  </li>

</template>

<style scoped>
  .count-btn {
    color: brown;
    background-color: white;
  }

  .show-view {
    color: greenyellow;
  }

  .active {
    color: red;
  }
</style>

<script setup>
import HelloWorld from './components/HelloWorld.vue'
import MyComp from './components/MyComp.vue'

import {ref, watch} from 'vue'

let count = ref(0)
watch(count, (newVal, oldVal) => {
    console.log(newVal, oldVal)
})

function onAdd() {
  console.log("onAdd called")
  count.value++
}

function onSub() {
  console.log("onSub called")
  count.value--
}

</script>

<template>
  <HelloWorld v-if="false" msg="hello world" />
  <MyComp title="hello" :count="count" flag="2" @add="onAdd" @sub="onSub"/>
  <div class="box" >
    aaa
  </div>
</template>

<style scoped>
  .box {
  width: 100px;
  height: 100px;
  background: red;

  position: relative;
  top: 50px;
}
</style>

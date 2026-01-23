<template>
    <h3 @click="emit('sub')">{{ title }}</h3>
    <div v-if="flag">联动{{ count }}</div>
</template>

<script setup>

defineProps({
    title: String,
    count: Number,
    flag: Number,
})

const emit = defineEmits(['add', 'sub'])


</script>

<style scoped></style>

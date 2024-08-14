<template>
    <button @click="add">increment</button>
    <div>{{ count }}</div>
    <button @click="minus">decrement</button>
</template>


<script setup>
const count = ref(0)
function add() {
    count.value++
}
function minus() {
    count.value--
}
</script>
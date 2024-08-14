<template>
    <div>Aboutttttt</div>
   
    <button @click="page">go to home</button>
</template>


<script setup>
function page(){
    navigateTo("/")
}
definePageMeta({
    layout:false
})
</script>
<template>
    <div>indexxxxx</div>
    
    <button @click="page">go to about</button>

</template>


<script setup>
function page(){
    navigateTo("about")
}
</script>
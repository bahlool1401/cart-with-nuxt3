<template>
  <div>
    <!-- <HomeWelcome/> -->
     <button @click="toggle">toggle</button><br>
    <component :is="myComponent"/>
  </div>
</template>

<script setup>
  const myComponent = shallowRef(resolveComponent("counter")) 
  function toggle (){
    myComponent.value = resolveComponent("homeWelcome")
  }
</script>



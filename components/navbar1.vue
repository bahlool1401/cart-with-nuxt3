<template>

    <nav class="bg-purple-900 shadow-lg p-3 text-white text-lg flex justify-between">
        <div class="flex">
            <NuxtLink class="mr-4" to="/">Home</NuxtLink>
            <NuxtLink class="mr-4" to="/iphone">Iphones</NuxtLink>
            <p class="mr-4">Cart ({{ cart.length }})</p>
            <p>Visit Count :{{ pageVisitCount }}</p>
        </div>
        <div v-if="auth.isAuthenticated">
            <NuxtLink to="/profile">Profile</NuxtLink>
            <button @click="logOut" class="ml-4">Logout</button>
        </div>
        <NuxtLink v-else to="/login">Login</NuxtLink>
    </nav>

</template>

<script setup>
const cart = useCart()
console.log('rrrrrrrrr', cart.value.length);

const auth = useAuth()

function logOut() {
    auth.value.isAuthenticated = false
}

const pageVisitCount =usePageVisitCount()
</script>
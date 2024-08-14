<template>
    <div>
        <div>

            <Head>
                <Title>
                    Nuxt3 - Iphone {{ name }}
                </Title>
            </Head>
            <div class="flex justify-center w-full mt-20">
                <div class="grid grid-cols-2">
                    <div>
                        <img :src="`/images/iphone-${$route.params.name}.webp`">
                    </div>
                    <div class="text-center">
                        <h1 class="text-3xl">Iphone {{ name }}</h1>
                        <button @click="addToCart" class="p-3 bg-indigo-900 text-white rounded-md mt-5 w-48">
                            <span v-if="!existIncart()">Buy Now</span>
                            <span v-if="existIncart()">Remove From Cart</span>
                        </button>
                    </div>
                </div>
            </div>
        </div>

    </div>
</template>


<script setup>
const route = useRoute()
const name = computed(() => {
    return route.params.name.replaceAll('-', ' ')
})

// useHead({
//     title:`Nuxt3 - Iphone  ${route.params.name}`
// })

const cart = useCart()
const fullName = computed(() => {
    return `iphone-${route.params.name}`
})

function existIncart() {
    return !!cart.value.find(cart => cart.name == fullName.value)
}


function addToCart() {
    if (!existIncart())
        cart.value.push({ name: fullName })
    else
        cart.value= cart.value.filter (c=>c.name !== fullName.value)
}



</script>
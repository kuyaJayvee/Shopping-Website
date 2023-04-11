<template>
     <div v-for="product in products" class="max-w-md shadow-md rounded p-3">
          <img :src="product.image" alt="Product img" class="object-contain h-48 w-96">
                <p class="font-semibold text-xl truncate p-2 py-1">{{ product.title }}</p>
                <p class="p-2 font-bold text-[1.2rem]">Price - ${{ product.price }}</p>
            <NuxtLink :to="`/products/${product.id}`" class="bg-green-500 text-white p-2 mx-2 rounded">View Details</NuxtLink>
     </div>
</template>

<script setup>
const { products } = defineProps(['products'])
</script>

<style scoped>

</style>
<template>
    <div class="container mx-auto p-8">
        <div class="grid grid-cols-4 gap-10">
            <ProductCard :products="products"></ProductCard>
        </div>
    </div>
</template>

<script setup>
const { data: products } = await useFetch('https://fakestoreapi.com/products');
useHead({
    title: "Products | Shoppe",
    meta: [
        { name: "description", content: "Original and cheap product" }
    ]
})
</script>

<style lang="scss" scoped></style>
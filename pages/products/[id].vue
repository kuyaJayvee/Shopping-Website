<template>
    <div>
       <ViewProduct :product="product"></ViewProduct>
    </div>
</template>

<script setup>
definePageMeta({
    layout: 'product'
})
const { id } = useRoute().params
const { data: product } = await useFetch("https://fakestoreapi.com/products/"+id, {key: id})
</script>

<style lang="scss" scoped>

</style>
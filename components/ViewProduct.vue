<template>
    <div class="container mx-auto p-8">
        <div class="grid lg:grid-cols-2 grid-cols-1 gap-11">
            <div>
                <img :src="product.image" alt="A product" class="md:max-w-lg">
            </div>
            <div class="mt-12">
                <p class="text-5xl font-bold py-3">{{ product.title }}</p>
                <p class="text-2xl font-semibold py-3">Price - ${{ product.price }}</p>
                <p class="text-xl">{{ product.description }}</p>
                <button @click.prevent="setLocalStorage" class="bg-green-500 px-2 py-3 rounded text-xl text-white mt-3 flex gap-2">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                        stroke="currentColor" class="w-6 h-6">
                        <path stroke-linecap="round" stroke-linejoin="round"
                            d="M2.25 3h1.386c.51 0 .955.343 1.087.835l.383 1.437M7.5 14.25a3 3 0 00-3 3h15.75m-12.75-3h11.218c1.121-2.3 2.1-4.684 2.924-7.138a60.114 60.114 0 00-16.536-1.84M7.5 14.25L5.106 5.272M6 20.25a.75.75 0 11-1.5 0 .75.75 0 011.5 0zm12.75 0a.75.75 0 11-1.5 0 .75.75 0 011.5 0z" />
                    </svg>
                    Add to Cart</button>
            </div>
        </div>
    </div>
</template>

<script setup>
const { product } = defineProps(['product'])
let items = [] 
const setLocalStorage = () => {
    if (localStorage.getItem('item')) {
        //existing item
        let item = JSON.parse(localStorage.getItem('item'))
        items.push(...item)
    }
    // new item
    items.push(product)
    localStorage.setItem('item', JSON.stringify(items))
}
</script>

<style scoped></style>
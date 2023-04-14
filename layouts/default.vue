<template>
    <div>
        <div class="bg-slate-100 shadow-md flex justify-around items-center py-7">
            <NuxtLink to="/" class="text-4xl font-bold text-green-400">Shoppe</NuxtLink>
            <ul class="flex items-center text-xl font-semibold gap-5 ">
                <li>
                    <NuxtLink to="/">Home</NuxtLink>
                </li>
                <li>
                    <NuxtLink to="/products">Product</NuxtLink>
                </li>
                <li>
                    <NuxtLink to="/about">About</NuxtLink>
                </li>
                <li class="relative">
                    <div class="relative">
                        <svg @click="openDrawer()" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
                            stroke-width="1.5" stroke="currentColor" class="w-11 h-9 cursor-pointer">
                            <path stroke-linecap="round" stroke-linejoin="round"
                                d="M2.25 3h1.386c.51 0 .955.343 1.087.835l.383 1.437M7.5 14.25a3 3 0 00-3 3h15.75m-12.75-3h11.218c1.121-2.3 2.1-4.684 2.924-7.138a60.114 60.114 0 00-16.536-1.84M7.5 14.25L5.106 5.272M6 20.25a.75.75 0 11-1.5 0 .75.75 0 011.5 0zm12.75 0a.75.75 0 11-1.5 0 .75.75 0 011.5 0z" />
                        </svg>
                        <span class="absolute -top-1 -right-1 bg-red-600 text-white rounded-full px-2 text-sm">{{ orderItems.length }}</span>
                    </div>
                    <div id="dropdown" class="z-10 absolute divide-y divide-gray-100 rounded-lg shadow sm:w-32 md:w-64 -left-4 bg-green-500 p-2 duration-500"
                        :class="isOpen ? 'inline-block' : 'hidden'">
                        <ul class="py-2 text-sm text-gray-700 dark:text-gray-200" aria-labelledby="dropdownDefaultButton">
                            <li v-for="item in orderItems" class="my-2">
                                <div class="flex px-3 justify-evenly gap-10 text-sm py-1 bg-slate-50 items-center rounded">
                                    <p class="text-slate-900">Price - ${{ item.price }}</p>
                                    <img class="object-cover w-11 h-11 rounded-full" :src="item.image" alt="product">
                                    <p><button @click.prevent="deleteItem(item.id)" class="bg-red-500 text-white px-2 py-1 rounded-full cursor-pointer hover:bg-red-400">X</button></p>
                                </div>
                            </li>
                        </ul>
                    </div>
                </li>
                <NuxtLink to="/login" class="bg-green-500 text-white p-1 px-2 rounded ml-2 hover:bg-green-600" id="login">Login</NuxtLink>
                <button class="bg-orange-500 text-white px-2 p-1 rounded hover:bg-orange-600">Signup</button>
            </ul>
        </div>
        <slot></slot>
    </div>
</template>

<script setup>
const isOpen = ref(false)
const orderItems = ref([])
const openDrawer = () => {
    return isOpen.value = !isOpen.value
}

const getLocalStorage = () => {
    const item = JSON.parse(localStorage.getItem('item') || [])
    orderItems.value = item
}

const deleteItem = (id) => {
    let item = JSON.parse(localStorage.getItem('item') || [])
    let itemIndex = item.findIndex((val) => val.id == id)

    if (itemIndex >= 0) {
        item.splice(itemIndex, 1)
        localStorage.setItem('item', JSON.stringify(item))
    }
}
onMounted(() => {
    getLocalStorage()
})
</script>

<style scoped>
.router-link-exact-active {
    color: #10B981;
}
#login {
    color: white;
}
</style>
<template>
    <div>
         <div class="bg-slate-100 shadow-md flex justify-around items-center py-8">
            <NuxtLink to="/" class="text-3xl font-bold text-green-400">Shoppe</NuxtLink>
            <ul class="flex items-center text-2xl font-semibold gap-5">
               <li><NuxtLink to="/">Home</NuxtLink></li>
               <li><NuxtLink to="/products">Product</NuxtLink></li>
               <li><NuxtLink to="/about">About</NuxtLink></li> 
            </ul>
        </div>
        <slot></slot>
    </div>
</template>

<script setup>
  
</script>

<style scoped>
.router-link-exact-active {
        color: #10B981;
    }
</style>
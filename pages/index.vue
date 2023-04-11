<template>
    <div class="container mx-auto p-3">
       <div class="grid grid-cols-2">
           <div class="flex flex-col justify-start gap-y-5 text-left py-10">
               <p class="text-9xl font-bold py-8 text-green-500">Shoppe!</p>
               <p class="text-4xl font-semibold">Shop affordable products Lorem ipsum dolor sit amet consectetur, adipisicing elit. Nobis, consectetur?</p>
           </div>
           <div>
              <img src="https://img.freepik.com/free-vector/online-flea-market-abstract-concept-illustration_335657-3782.jpg?w=740&t=st=1681199007~exp=1681199607~hmac=917da69d25d5c9eeed30db390d5564f51a523b95ac4b7c0e6109c87d10a20705"/>
           </div>
       </div>
    </div>
</template>

<script setup>
useHead({
    title: "Home | Shoppe",
    meta: [
        {name: "description", content: "Original and cheap product"}
    ]
})
</script>

<style lang="scss" scoped>

</style>
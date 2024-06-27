<template>
  <div>
   <ul class="flex justify-center items-center gap-4 flex-wrap">
     <li v-for="filme in filmes" :key="filme.id" class="bg-white rounded-lg shadow-md w-80 mb-4">
       <div class="relative">
         <img :src="`${filme.image}`" alt="" class="w-full h-60 object-cover">
         <p class="absolute bottom-0 left-0 right-0 bg-black text-white text-center p-2">{{ filme.name }}</p>
       </div>
       <div class="p-4">
         <div class="flex mb-4">
           <p v-for="genero in filme.genres" :key="genero" class="ml-4 mr-4 bg-blue-500 rounded-xl p-1 text-white">
             {{ genero }}
           </p>
         </div>
         <p>
           {{ filme.description }}
         </p>
         <div class="flex aling-center mt-4">
           <p>
             Rating: ({{ filme.rating }})
           </p>
           <div>
             <span v-for="i in 5" :key="i" :class="{ 'filled': i <= filme.rating } " style="font-size: 30px;">★</span>
           </div>
         </div>
       </div>
     </li>
   </ul>
  </div>
</template>

<script setup>
import { items } from "./movies.json";
import { ref } from 'vue'
const filmes = ref(items)
</script>

<style>
.filled {
  color: gold;
}
img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
</style>
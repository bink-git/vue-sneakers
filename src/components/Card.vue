<script setup>
import { ref } from 'vue'

defineProps({
  title: String,
  imageUrl: String,
  price: Number,
  isFavorite: Boolean,
  isAdded: Boolean,
  onClickFavorite: Function,
  onClickAdd: Function
})

// const isLiked = ref(false)

// const onClick = () => {
//   isFavorite = !isFavorite
// }
</script>

<template>
  <div
    class="relative flex flex-col w-full border border-slate-100 rounded-xl p-8 cursor-pointer transition hover:shadow-xl hover:transform hover:-translate-y-2"
  >
    <div @click="onClickFavorite" class="absolute top-8 left-8">
      <img :src="!isFavorite ? '/like-1.svg' : '/like-2.svg'" alt="Favorite" />
    </div>

    <img :src="imageUrl" class="w-full" alt="Sneaker" />

    <p>{{ title }}</p>

    <div class="flex justify-between mt-5">
      <div class="flex flex-col gap-2">
        <span class="text-slate-200">Price:</span>
        <span class="font-bold">{{ price }} $</span>
      </div>

      <img @click="onClickAdd" :src="isAdded ? '/checked.svg' : '/plus.svg'" alt="Plus" />
    </div>
  </div>
</template>

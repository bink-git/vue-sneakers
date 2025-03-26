<script setup>
import CartItem from './CartItem.vue'
</script>

<template>
  <div class="flex flex-col gap-5">
    <CartItem title="Nike Blazer Mid Suede" :price="1000" img="/sneakers/sneakers-1.jpg" />
    <CartItem title="Nike Blazer Mid Suede" :price="1200" img="/sneakers/sneakers-2.jpg" />
    <CartItem title="Nike Blazer Mid Suede" :price="1200" img="/sneakers/sneakers-3.jpg" />
  </div>
</template>

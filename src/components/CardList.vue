<script setup>
import Card from './Card.vue'

const onClickAdd = () => {
  alert('Add to cart')
}
</script>

<template>
  <div class="grid gap-5 sm:grid-cols-2 xl:grid-cols-3 2xl:grid-cols-4">
    <Card
      title="Nike Blazer Mid Suede"
      :price="1000"
      :isFavorite="true"
      :isAdded="false"
      :onClickAdd="onClickAdd"
      img="/sneakers/sneakers-1.jpg"
    />
    <Card
      title="Nike Blazer Suede"
      :price="1200"
      :isFavorite="false"
      img="/sneakers/sneakers-2.jpg"
    />
    <Card title="Nike Mid Suede" :price="1300" :isFavorite="false" img="/sneakers/sneakers-3.jpg" />
    <Card
      title="Nike Blazer Mid"
      :price="1400"
      :isFavorite="false"
      img="/sneakers/sneakers-4.jpg"
    />
    <Card title="Nike Suede" :price="1500" :isFavorite="false" img="/sneakers/sneakers-5.jpg" />
    <Card
      title="Nike Blazer Mid Suede"
      :price="1000"
      :isFavorite="false"
      img="/sneakers/sneakers-1.jpg"
    />
  </div>
</template>

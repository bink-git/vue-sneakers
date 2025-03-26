<script setup>
import CartItemList from './CartItemList.vue'
import DrawerHearer from './DrawerHearer.vue'
</script>

<template>
  <div class="fixed z-10 top-0 h-full w-full bg-black opacity-70" />
  <div class="flex flex-col fixed z-10 top-0 h-full right-0 w-96 bg-white px-10 py-7">
    <div class="flex-1">
      <DrawerHearer />
      <CartItemList />
    </div>

    <div class="flex flex-col justify-between">
      <div>
        <div class="flex flex-col gap-5">
          <div class="flex items-end gap-2">
            <span>Total:</span>
            <div class="flex-1 border-b border-dashed" />
            <span class="font-bold">1000 $</span>
          </div>

          <div class="flex items-end gap-2">
            <span>Tax 5%:</span>
            <div class="flex-1 border-b border-dashed" />
            <span class="font-bold">50 $</span>
          </div>
        </div>

        <button
          class="flex justify-center items-center gap-3 w-full py-3 mt-10 bg-lime-500 text-white rounded-xl transition active:bg-lime-700 hover:bg-lime-600"
        >
          Order
          <img src="/arrow-next.svg" alt="Arrow" />
        </button>
      </div>
    </div>
  </div>
</template>

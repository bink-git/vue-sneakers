<script setup>
import { onMounted, reactive, ref, watch } from 'vue'
import axios from 'axios'
import CardList from '../components/CardList.vue'
import Header from '../components/Header.vue'

const items = ref([])

const filters = reactive({
  sortBy: '',
  searchQuery: ''
})

const onChangeSelect = (event) => {
  filters.sortBy = event.target.value
}

const fetchItems = async () => {
  try {
    const params = {
      sortBy: filters.sortBy,
      searchQuery: filters.searchQuery
    }

    const { data } = await axios.get('https://604781a0efa572c1.mokky.dev/items')
    items.value = data.slice(0, 12)
  } catch (error) {
    console.error(error)
  }
}

onMounted(fetchItems)

watch(filters, fetchItems)
</script>

<template>
  <div class="bg-white w-3/5 m-auto rounded-xl shadow-xl shadow-grey-200 mt-20">
    <Header />

    <div class="p-10">
      <div class="flex flex-col xl:flex-row xl:justify-between xl:items-center mb-10 gap-4">
        <h1 class="text-3xl font-bold">All sneakers</h1>
        <div class="flex items-center gap-4">
          <select
            @change="onChangeSelect"
            class="py-2 px-3 border border-gray-200 focus:border-gray-400 rounded-md focus:outline-none"
          >
            <option value="name">By name</option>
            <option value="price">By price (low)</option>
            <option value="-price">By price (high)</option>
          </select>
          <div class="relative">
            <input
              type="text"
              class="border border-gray-200 rounded-md py-2 pl-10 pr-4 focus:outline-none focus:border-gray-400"
              placeholder="Search..."
            />
            <div class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none">
              <img src="/search.svg" />
            </div>
          </div>
        </div>
      </div>

      <CardList :items="items" />
    </div>
  </div>
</template>

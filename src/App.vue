<template>
  <main class="flex flex-col min-h-screen">
    <nav class="bg-custom-red w-full flex justify-around sm:justify-between items-center py-4 sm:px-6">
      <router-link :to="{ name: 'home' }" class="text-white text-2xl font-bold ml-4">
        <img src="@/assets/images/logo.jpg" alt="Logo" class="rounded-full w-14 ">
      </router-link>
      <container class=" w-64 sm:w-96 ">
        <CustomSelect v-model="selectedOption" :options="languageOptions"
          select-class=" !h-11 !text-gray-500 !border-gray-500 focus:!ring-gray-500 focus:!border-gray-500" />
      </container>

    </nav>

    <router-view class="flex-grow"></router-view>
    <footer class="bg-custom-red text-white text-center p-1">
      <p>&copy; RS Labs. 2025 All rights reserved</p>
    </footer>
  </main>
</template>

<script setup>
import { ref } from 'vue'
import CustomSelect from '@/components/CustomSelect.vue'

const selectedOption = ref('1')
const languageOptions = ref([
  { value: '1', label: 'عربي' },
  { value: '2', label: 'English' }
])
</script>
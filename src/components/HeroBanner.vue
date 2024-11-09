<template>
  <div class="relative h-screen">
    <div class="absolute inset-0">
      <img
        src="https://images.unsplash.com/photo-1626814026160-2237a95fc5a0?auto=format&fit=crop&w=1920"
        alt="Hero Banner"
        class="h-full w-full object-cover"
      />
      <div class="absolute inset-0 bg-gradient-to-r from-black/80 via-black/50 to-transparent" />
    </div>
    <div class="relative flex h-full items-center px-4 pb-20 pt-40 sm:px-6 lg:px-8">
      <div class="max-w-2xl">
        <h1 class="text-4xl font-bold tracking-tight text-white sm:text-5xl md:text-6xl">
          Stranger Things
        </h1>
        <p class="mt-4 max-w-xl text-xl text-gray-300">
          When a young boy vanishes, a small town uncovers a mystery involving secret experiments, terrifying supernatural forces and one strange little girl.
        </p>
        <div class="mt-8 flex space-x-4">
          <button class="flex items-center space-x-2 rounded-md bg-white px-8 py-3 font-semibold text-black hover:bg-gray-200">
            <Play class="h-6 w-6" />
            <span>Play</span>
          </button>
          <button class="flex items-center space-x-2 rounded-md bg-gray-600/80 px-8 py-3 font-semibold text-white hover:bg-gray-600">
            <Info class="h-6 w-6" />
            <span>More Info</span>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { Play, Info } from 'lucide-vue-next'
</script>
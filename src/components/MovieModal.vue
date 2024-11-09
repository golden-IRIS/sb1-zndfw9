<template>
  <div class="fixed inset-0 z-50 flex items-center justify-center px-4">
    <div class="fixed inset-0 bg-black/70" @click="$emit('close')" />
    <div class="relative max-h-[90vh] w-full max-w-4xl overflow-y-auto rounded-lg bg-zinc-900">
      <button 
        @click="$emit('close')"
        class="absolute right-4 top-4 z-10 rounded-full bg-black/50 p-2 text-white hover:bg-black/70"
      >
        <X class="h-6 w-6" />
      </button>
      <div>
        <div class="relative h-[400px]">
          <img 
            :src="movie.image" 
            :alt="movie.title"
            class="h-full w-full object-cover"
          />
          <div class="absolute inset-0 bg-gradient-to-t from-zinc-900" />
        </div>
        <div class="px-6 pb-8 pt-4">
          <h2 class="text-3xl font-bold text-white">{{ movie.title }}</h2>
          <div class="mt-2 flex items-center space-x-2 text-sm text-gray-400">
            <span>{{ movie.year }}</span>
            <span>•</span>
            <span>{{ movie.rating }}</span>
            <span>•</span>
            <span>{{ movie.duration }}</span>
          </div>
          <p class="mt-4 text-gray-300">{{ movie.description }}</p>
          <div class="mt-6 flex space-x-4">
            <button class="flex items-center space-x-2 rounded-md bg-white px-6 py-2 font-semibold text-black hover:bg-gray-200">
              <Play class="h-5 w-5" />
              <span>Play</span>
            </button>
            <button class="flex items-center space-x-2 rounded-md border border-gray-400 px-6 py-2 text-white hover:bg-white/10">
              <Plus class="h-5 w-5" />
              <span>My List</span>
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { X, Play, Plus } from 'lucide-vue-next'
import type { Movie } from '../types'

defineProps<{
  movie: Movie
}>()

defineEmits<{
  (e: 'close'): void
}>()
</script>
<template>
  <div class="px-4 sm:px-6 lg:px-8">
    <h2 class="mb-4 text-xl font-semibold text-white">{{ title }}</h2>
    <div class="relative group">
      <button 
        @click="scroll('left')" 
        class="absolute left-0 top-0 z-40 hidden h-full w-12 items-center justify-center bg-black/50 text-white group-hover:flex"
      >
        <ChevronLeft class="h-8 w-8" />
      </button>
      <div ref="scrollContainer" class="flex space-x-4 overflow-x-hidden scroll-smooth">
        <div 
          v-for="movie in movies" 
          :key="movie.id" 
          class="flex-none cursor-pointer transition duration-300 hover:scale-105"
          @click="$emit('select-movie', movie)"
        >
          <div class="relative h-[200px] w-[300px]">
            <img 
              :src="movie.image" 
              :alt="movie.title"
              class="h-full w-full rounded-md object-cover"
            />
            <div class="absolute inset-0 rounded-md opacity-0 transition duration-300 hover:bg-black/50 hover:opacity-100">
              <div class="flex h-full items-end p-4">
                <div>
                  <h3 class="text-lg font-semibold text-white">{{ movie.title }}</h3>
                  <div class="mt-1 flex items-center space-x-2 text-sm text-gray-300">
                    <span>{{ movie.rating }}</span>
                    <span>•</span>
                    <span>{{ movie.duration }}</span>
                    <span>•</span>
                    <span>{{ movie.year }}</span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <button 
        @click="scroll('right')" 
        class="absolute right-0 top-0 z-40 hidden h-full w-12 items-center justify-center bg-black/50 text-white group-hover:flex"
      >
        <ChevronRight class="h-8 w-8" />
      </button>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import { ChevronLeft, ChevronRight } from 'lucide-vue-next'
import type { Movie } from '../types'

defineProps<{
  title: string
  movies: Movie[]
}>()

defineEmits<{
  (e: 'select-movie', movie: Movie): void
}>()

const scrollContainer = ref<HTMLElement | null>(null)

const scroll = (direction: 'left' | 'right') => {
  if (!scrollContainer.value) return
  const scrollAmount = 300
  scrollContainer.value.scrollBy({
    left: direction === 'left' ? -scrollAmount : scrollAmount,
    behavior: 'smooth'
  })
}
</script>
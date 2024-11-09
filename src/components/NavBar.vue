<template>
  <nav class="fixed top-0 z-50 w-full bg-gradient-to-b from-black/80 to-transparent">
    <div class="mx-auto flex items-center justify-between px-4 py-4">
      <div class="flex items-center space-x-8">
        <div class="text-red-600 font-bold text-2xl tracking-wider">
          <PlaySquare class="h-8 w-24" />
          <span>NETFLIX</span>
        </div>
        <div class="hidden space-x-4 md:flex">
          <a v-for="item in menuItems" :key="item" href="#" class="text-sm text-gray-300 hover:text-white">
            {{ item }}
          </a>
        </div>
      </div>
      <div class="flex items-center space-x-4">
        <Search class="h-5 w-5 text-gray-300" />
        <Bell class="h-5 w-5 text-gray-300" />
        <button class="flex items-center space-x-2 rounded-md bg-red-600 px-4 py-2 text-sm font-semibold text-white hover:bg-red-700">
          <UserCircle2 class="h-5 w-5" />
          <span>Sign In</span>
        </button>
      </div>
    </div>
  </nav>
</template>

<script setup lang="ts">
import { PlaySquare, Search, Bell, UserCircle2 } from 'lucide-vue-next'

const menuItems = ['Home', 'TV Shows', 'Movies', 'New & Popular', 'My List']
</script>
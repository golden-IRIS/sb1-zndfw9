<template>
  <div class="min-h-screen bg-black text-white">
    <NavBar />
    <HeroBanner />
    <div class="relative z-10 -mt-32 space-y-8 pb-8">
      <MovieRow title="Trending Now" :movies="trendingMovies" />
      <MovieRow title="Popular on Netflix" :movies="popularMovies" />
      <MovieRow title="New Releases" :movies="newReleases" />
    </div>
    <MovieModal v-if="selectedMovie" :movie="selectedMovie" @close="selectedMovie = null" />
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import NavBar from './components/NavBar.vue'
import HeroBanner from './components/HeroBanner.vue'
import MovieRow from './components/MovieRow.vue'
import MovieModal from './components/MovieModal.vue'
import type { Movie } from './types'

const selectedMovie = ref<Movie | null>(null)

const trendingMovies = [
  {
    id: 1,
    title: "Stranger Things",
    description: "When a young boy vanishes, a small town uncovers a mystery involving secret experiments, terrifying supernatural forces and one strange little girl.",
    image: "https://images.unsplash.com/photo-1626814026160-2237a95fc5a0?auto=format&fit=crop&w=800",
    year: 2022,
    rating: "TV-14",
    duration: "1h 45m"
  },
  {
    id: 2,
    title: "The Crown",
    description: "This drama follows the political rivalries and romance of Queen Elizabeth II's reign and the events that shaped the second half of the 20th century.",
    image: "https://images.unsplash.com/photo-1536440136628-849c177e76a1?auto=format&fit=crop&w=800",
    year: 2023,
    rating: "TV-MA",
    duration: "1h 58m"
  },
  // Add more movies as needed
]

const popularMovies = [
  {
    id: 3,
    title: "Breaking Bad",
    description: "A high school chemistry teacher turned methamphetamine manufacturer partners with a former student to secure his family's financial future as he battles terminal lung cancer.",
    image: "https://images.unsplash.com/photo-1594909122845-11baa439b7bf?auto=format&fit=crop&w=800",
    year: 2021,
    rating: "TV-MA",
    duration: "2h 10m"
  },
  // Add more movies
]

const newReleases = [
  {
    id: 4,
    title: "The Witcher",
    description: "Geralt of Rivia, a mutated monster-hunter for hire, journeys toward his destiny in a turbulent world where people often prove more wicked than beasts.",
    image: "https://images.unsplash.com/photo-1633019601519-d65d1817cbd7?auto=format&fit=crop&w=800",
    year: 2023,
    rating: "TV-MA",
    duration: "1h 55m"
  },
  // Add more movies
]
</script>